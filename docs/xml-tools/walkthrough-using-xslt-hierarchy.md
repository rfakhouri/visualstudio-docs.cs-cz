---
title: 'Průvodce: Používání hierarchie XSLT'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 65af5f973f9440ac781a8af1042700cf89acee1c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53834721"
---
# <a name="walkthrough-use-xslt-hierarchy"></a>Průvodce: Používání hierarchie XSLT

Nástroj XSLT Hierarchy zjednodušuje mnoho úloh vývoje XML. Šablony stylů XSLT se často používá `includes` a `imports` pokyny. Kompilace se spouští z hlavní šablony stylů, ale když se zobrazí chyba v důsledku kompilaci šablony stylů XSLT, chyba mohou pocházet z jiného zdroje než hlavní šablony stylů. Oprava chyby nebo úpravu šablony stylů může vyžadovat přístup k vkládaného nebo importovaného šablony stylů. Krokování stylů v ladicím programu může otevřít zahrnuté a importované šablony stylů a můžete chtít přidat zarážku v určitém okamžiku v jednom nebo více zahrnuty šablony stylů.

Jiný scénář, kde může být užitečný nástroj hierarchie XSLT je umístění zarážky na předdefinované šablony pravidla. Šablony pravidel jsou speciální šablon vygenerována pro každý druh šablony stylů a volané `xsl:apply-templates` při žádná šablona odpovídá uzlu. Ladicí program XSLT provádět ladění v předdefinované šablony pravidla, vygeneruje soubor s pravidly v dočasné složce a jejich kompiluje spolu s hlavní šablony stylů. Bez krokování s vnořením do kódu z některých `xsl:apply-template`, může být obtížné najít šablony stylů, které byly součástí hlavní šablony stylů nebo k vyhledání a otevření s integrovanou šablonu pravidla šablony stylů.

V příkladu v tomto tématu ukazuje ladění v odkazované šablony stylů.

## <a name="to-debug-in-a-referenced-style-sheet"></a>Chcete-li ladit v odkazované šablony stylů

1. Otevřete dokument XML v sadě Visual Studio. Tento příklad používá v následujícím dokumentu:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <?xml-stylesheet type="text/xsl" href="xslinclude.xsl"?>
    <COLLECTION>
      <BOOK>
        <TITLE>Lover Birds</TITLE>
        <AUTHOR>Cynthia Randall</AUTHOR>
        <PUBLISHER>Lucerne Publishing</PUBLISHER>
      </BOOK>
      <BOOK>
        <TITLE>The Sundered Grail</TITLE>
        <AUTHOR>Eva Corets</AUTHOR>
        <PUBLISHER>Lucerne Publishing</PUBLISHER>
      </BOOK>
      <BOOK>
        <TITLE>Splish Splash</TITLE>
        <AUTHOR>Paula Thurman</AUTHOR>
        <PUBLISHER>Scootney</PUBLISHER>
      </BOOK>
    </COLLECTION>
    ```

1. Přidejte následující *xslincludefile.xsl*:

    ```xml
    <?xml version='1.0'?>
    <xsl:stylesheet version="1.0"
          xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
          xml:space="preserve">

    <xsl:template match="TITLE">
       Title - <xsl:value-of select="."/><BR/>
    </xsl:template>

    <xsl:template match="AUTHOR">
       Author - <xsl:value-of select="."/><BR/>
    </xsl:template>

    <xsl:template match="PUBLISHER">
       Publisher - <xsl:value-of select="."/><BR/><!-- removed second <BR/> -->
    </xsl:template>

    </xsl:stylesheet>
    ```

3.  Přidejte následující *xslinclude.xsl* souboru:

    ```xml
    <?xml version='1.0'?>
    <xsl:stylesheet version="1.0"
          xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

      <xsl:output method="xml" omit-xml-declaration="yes"/>

      <xsl:template match="/">
        <xsl:for-each select="COLLECTION/BOOK">
          <xsl:apply-templates select="TITLE"/>
          <xsl:apply-templates select="AUTHOR"/>
          <xsl:apply-templates select="PUBLISHER"/>
          <BR/>
          <!-- add this -->
        </xsl:for-each>
      </xsl:template>

      <!-- The following template rule will not be called,
      because the related template in the including stylesheet
      is called. If we move this template so that
      it follows the xsl:include instruction, this one
      will be called instead.-->
      <xsl:template match="TITLE">
        <DIV STYLE="color:blue">
          Title: <xsl:value-of select="."/>
        </DIV>
      </xsl:template>

      <xsl:include href="xslincludefile.xsl" />
    </xsl:stylesheet>
    ```

4.  Přidejte zarážku na instrukci `<xsl:include href="xslincludefile.xsl" />`.

5.  Spusťte ladění.

6.  Pokud ladicí program se zastaví podle instrukce `<xsl:include href="xslincludefile.xsl" />`, stiskněte **Krokovat s vnořením** tlačítko. Ladění lze pokračovat v odkazované šablony stylů. V hierarchii je viditelná a Návrhář zobrazí správné cestě.

## <a name="see-also"></a>Viz také:

- [Návod: XSLT profiler](../xml-tools/walkthrough-xslt-profiler.md)