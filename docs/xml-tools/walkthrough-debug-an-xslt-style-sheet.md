---
title: 'Průvodce: Ladění stylů XSLT'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 3db9fa5a-f619-4cb6-86e7-64b364e58e5d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2d3b178fd22cbb22010e90080520f0b5c3a54ca
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54921840"
---
# <a name="walkthrough-debug-an-xslt-style-sheet"></a>Průvodce: Ladění stylů XSLT

Kroky v tomto názorném postupu ukazují, jak použít ladicí program XSLT. Kroky zahrnují zobrazení proměnné, nastavovat zarážky a krokování kódu. Šablony stylů vyhledá všechny knihy, které náklady pod průměrnou cenu knih.

## <a name="to-prepare-for-this-walkthrough"></a>Příprava pro Tento názorný postup

1.  Zavřete všechna otevřená řešení.

2.  Zkopírujte dva ukázkové soubory do místního počítače.

## <a name="start-debugging"></a>Spustit ladění

### <a name="to-start-debugging"></a>Pro spuštění ladění

1.  Z **souboru** nabídky, přejděte k **otevřít**a klikněte na tlačítko **souboru**.

2.  Vyhledejte *belowAvg.xsl* souboru a klikněte na tlačítko **otevřít**.

     Šablona stylů je otevřen v editoru XML.

3.  Klikněte na tlačítko Procházet (**...** ) na **vstup** pole v okně Vlastnosti dokumentu.

4.  Vyhledejte *books.xml* souboru a klikněte na tlačítko **otevřít**.

     Tím se nastaví zdrojový soubor dokumentu, který slouží k transformaci XSLT.

5.  Klikněte pravým tlačítkem myši `xsl:if` počáteční značka, přejděte na **zarážku**a klikněte na tlačítko **vložit zarážku**.

6.  Klikněte na tlačítko **ladění XSL** tlačítko na panelu nástrojů editoru XML.

To spustí proces ladění a několik nových oken, které jsou používány ladicí program.

Existují dvě okna, které zobrazují vstupní dokument a styly listu. Ladicí program používá tyto windows zobrazit aktuální stav provádění. Ladicí program je umístěn na `xsl:if` prvku šablony stylů a na prvním uzlu v knize *books.xml* souboru.

**Lokální** okně se zobrazí všechny místní proměnné a jejich aktuálními hodnotami. To zahrnuje proměnné definované v šabloně stylů a také proměnné, které ladicí program používá ke sledování uzly, které jsou momentálně v kontextu.

**Výstupu XSL** okně se zobrazí výstup této transformace XSL. Toto okno je oddělená od **výstup Visual Studia** okna.

## <a name="watch-window"></a>Kukátko – okno

### <a name="to-use-the-watch-window"></a>Pokud chcete použít okno kukátka

1.  Z **ladění** nabídky, přejděte k **Windows**, přejděte na **Watch**a klikněte na tlačítko **kukátko 1**.

     Díky tomu **kukátko 1** okno viditelné.

2.  Typ `$bookAverage` v **název** pole a stiskněte klávesu **Enter**.

     Hodnota `$bookAverage` proměnné se zobrazí v okně.

3.  Typ `self::node()` v **název** pole a stiskněte klávesu **Enter**.

     `self::node()` je výraz XPath, který se vyhodnotí jako aktuální uzel kontextu. Hodnota `self::node()` výraz XPath je první uzel knihy. To změní, když jsme průběhu transformace.

4.  Rozbalte `self::node()` uzel a potom rozbalte `price` uzlu.

     To umožňuje zobrazit hodnotu cenu knih a můžete snadno porovnat tak, `$bookAverage` hodnotu. Vzhledem k tomu knihy cena je nižší než průměr, `xsl:if` podmínku uspěli.

## <a name="step-through-the-code"></a>Krokovat kód
 Ladicí program umožňuje spustit jeden řádek kódu v čase.

### <a name="to-step-through-the-code"></a>Chcete-li si kód

1.  Stisknutím klávesy **F5** pokračujte.

     Protože splněna první uzel knihy `xsl:if` podmínka, uzel kniha je přidána do **výstupu XSL** okna. Ladicí program pokračuje v provádění, dokud je znovu umístěn na `xsl:if` element v šabloně stylů. Ladicí program je teď umístěný na druhém uzlu adresáře v *books.xml* souboru.

     V **kukátko 1** okno `self::node()` hodnota nezmění na druhý uzel knihy. Prozkoumáním hodnota elementu cena můžete určit, že cena je vyšší než průměr, tedy `xsl:if` podmínka by selhat.

2.  Stisknutím klávesy **F5** pokračujte.

     Protože druhý uzel knihy nesplňuje `xsl:if` podmínku, uzel knihy není přidán do **výstupu XSL** okna. Ladicí program pokračuje v provádění, dokud je znovu umístěn na `xsl:if` element v šabloně stylů. Ladicí program je nyní umístěn na třetí `book` uzlu *books.xml* souboru.

     V **kukátko 1** okno `self::node()` hodnota nezmění na třetí uzel knihy. Porovnáním hodnoty `price` element, můžete určit, že cena je nižší než průměr, tedy `xsl:if` podmínku uspěli.

3.  Stisknutím klávesy **F5** pokračujte.

     Vzhledem k tomu, `xsl:if` byla splněna podmínka, třetí kniha je přidána do **výstupu XSL** okna. Byly zpracovány všechny knihy v dokumentu XML a ladicí program se zastaví.

## <a name="sample-files"></a>Ukázkové soubory

Následující dva soubory jsou používány návodu.

### <a name="belowavgxsl"></a>belowAvg.xsl

```xml
<?xml version='1.0'?>
<xsl:stylesheet version="1.0"
      xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output method="xml" encoding="utf-8"/>
  <xsl:template match="/">
    <xsl:variable name="bookCount" select="count(/bookstore/book)"/>
    <xsl:variable name="bookTotal" select="sum(/bookstore/book/price)"/>
    <xsl:variable name="bookAverage" select="$bookTotal div $bookCount"/>
    <books>
      <!--Books That Cost Below Average-->
      <xsl:for-each select="/bookstore/book">
        <xsl:if test="price < $bookAverage">
          <xsl:copy-of select="."/>
        </xsl:if>
      </xsl:for-each>
    </books>
  </xsl:template>
</xsl:stylesheet>
```

### <a name="booksxml"></a>Books.XML

```xml
<?xml version='1.0'?>
<!-- This file represents a fragment of a book store inventory database -->
<bookstore>
  <book genre="autobiography" publicationdate="1981" ISBN="1-861003-11-0">
    <title>The Autobiography of Benjamin Franklin</title>
    <author>
      <first-name>Benjamin</first-name>
      <last-name>Franklin</last-name>
    </author>
    <price>8.99</price>
  </book>
  <book genre="novel" publicationdate="1967" ISBN="0-201-63361-2">
    <title>The Confidence Man</title>
    <author>
      <first-name>Herman</first-name>
      <last-name>Melville</last-name>
    </author>
    <price>11.99</price>
  </book>
  <book genre="philosophy" publicationdate="1991" ISBN="1-861001-57-6">
    <title>The Gorgias</title>
    <author>
      <name>Plato</name>
    </author>
    <price>9.99</price>
  </book>
</bookstore>
```

## <a name="see-also"></a>Viz také:

- [Ladění XSLT](../xml-tools/debugging-xslt.md)