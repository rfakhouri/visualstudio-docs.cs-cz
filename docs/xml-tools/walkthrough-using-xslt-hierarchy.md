---
title: 'Návod: Použití XSLT hierarchie | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: a4259a06d79588983e3591510c40e119bc4fcb3b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-using-xslt-hierarchy"></a>Návod: Použití hierarchie XSLT

Nástroj XSLT Hierarchy zjednodušuje celou řadu úloh vývoj XML. Stylů XSLT často používá `includes` a `imports` pokyny. Kompilace se spouští z hlavní šablony stylů, ale když se zobrazí chybu v důsledku kompilování stylů XSLT, chyba mohou pocházet z jiného zdroje než hlavní šablony stylů. Oprava chyby nebo úpravou šablony stylů může vyžadovat přístup k zahrnuté ani importované šablony stylů. Procházení šablony stylů v ladicím programu může zobrazit zahrnuté a importované šablony stylů a můžete chtít přidat zarážky v určitém okamžiku v jedné nebo více součástí šablony stylů.

Jiný scénář, kde může být užitečná nástroj XSLT Hierarchy je uvedení zarážky předdefinované šablony pravidel. Šablony pravidel jsou speciální šablony vygenerovat pro každý režimu šablony stylů a volá `xsl:apply-templates` když žádné jiné šablony, odpovídá uzlu. Ladicí program XSLT implementovat ladění předdefinované šablony pravidel, vygeneruje soubor s pravidly v dočasné složce a zkompiluje je společně s hlavní šablony stylů. Bez zanoříte se do kód z některé `xsl:apply-template`, může být obtížné najít stylů, které byly součástí hlavní šablony stylů nebo můžete najít a otevřít šablony stylů pomocí předdefinované šablony pravidel.

Příklad v tomto tématu ukazuje ladění pomocí odkazovaného stylů.

## <a name="to-debug-in-a-referenced-style-sheet"></a>Chcete-li ladit v odkazované šabloně stylů.

1. Otevřete dokument XML v sadě Visual Studio. Tento příklad používá následující `collection.xml` dokumentu.  
  
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

1. Přidejte následující `xslincludefile.xsl`:

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
  
3.  Přidejte následující `xslinclude.xsl` souboru:  
  
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
  
4.  Přidejte zarážku u instrukce `<xsl:include href="xslincludefile.xsl" />`.
  
5.  Spusťte ladění.  
  
6.  Při zastavení ladicího programu u instrukce `<xsl:include href="xslincludefile.xsl" />`, stiskněte **Krokovat s vnořením** tlačítko. Všimněte si, že je ladění můžete pokračovat v odkazované šablony stylů. V hierarchii je viditelná a Návrhář zobrazí správné cestě.  
  
## <a name="see-also"></a>Viz také

[Návod: Profiler XSLT](../xml-tools/walkthrough-xslt-profiler.md)