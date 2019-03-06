---
title: Ladění šablon stylů XSLT
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 3db9fa5a-f619-4cb6-86e7-64b364e58e5d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e787ca3d2d29f04d6af27a5f36f1f84c9d0bc9f4
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526630"
---
# <a name="walkthrough-debug-an-xslt-style-sheet"></a>Návod: Ladění stylů XSLT

Kroky v tomto názorném postupu ukazují, jak použít ladicí program XSLT. Kroky zahrnují zobrazení proměnné, nastavovat zarážky a krokování kódu. Ladicí program umožňuje spustit jeden řádek kódu v čase.

Příprava pro tento návod, nejprve zkopírovat dva [ukázkové soubory](#sample-files) do místního počítače. Jedna je šablony stylů a jeden je soubor XML, který použijeme jako vstup pro šablony stylů. Šablony stylů, které používáme v tomto podrobném návodu, najde všechny knihy, jejichž cena je nižší než průměrnou cenu knih.

> [!NOTE]
> Ladicí program XSLT je dostupná pouze v edici Enterprise systému Visual Studio.

## <a name="start-debugging"></a>Spustit ladění

1. Z **souboru** nabídce zvolte **otevřít** > **souboru**.

2. Vyhledejte *níže average.xsl* soubor a zvolte **otevřít**.

   Šablony stylů se otevře v editoru XML.

3. Klikněte na tlačítko Procházet (**...** ) na **vstup** pole v okně Vlastnosti dokumentu. (Pokud **vlastnosti** okno se nezobrazuje, klepněte pravým tlačítkem myši na otevření souboru v editoru a klikněte na tlačítko **vlastnosti**.)

4. Vyhledejte *books.xml* souboru a klikněte na tlačítko **otevřít**.

   Tím se nastaví zdrojový soubor dokumentu, který slouží k transformaci XSLT.

5. Nastavte [zarážku](../debugger/using-breakpoints.md) na řádku 12 *níže average.xsl*. Provést několika způsoby:

   - Klikněte na okraj editoru na řádek 12.

   - Klikněte na libovolné místo na řádku 12 a potom stiskněte klávesu **F9**.

   - Klikněte pravým tlačítkem myši `xsl:if` počáteční značka a klikněte na tlačítko **zarážku** > **vložit zarážku**.

      ![Vložit zarážku v souboru XSL v sadě Visual Studio](media/insert-breakpoint.PNG)

6. V panelu nabídky zvolte **XML** > **spustit ladění XSLT** (nebo stiskněte klávesu **Alt**+**F5**).

   Spuštění ladění procesu.

   V editoru, ladicího programu je umístěn na `xsl:if` elementu šablony stylů. Další soubor s názvem *níže average.xml* otevře v editoru; Toto je výstupní soubor, který naplní se jako každý uzel ve vstupním souboru *books.xml* se zpracovává.

   **Automatické hodnoty**, **lokální**, a **kukátko 1** okna se zobrazí v dolní části okna nástroje Visual Studio. **Lokální** okně se zobrazí všechny místní proměnné a jejich aktuálními hodnotami. To zahrnuje proměnné definované v šabloně stylů a také proměnné, které ladicí program používá ke sledování uzly, které jsou momentálně v kontextu.

## <a name="watch-window"></a>Kukátko – okno

Přidáme do dvou proměnných **kukátko 1** okna tak, aby se po zpracování vstupního souboru jsme můžete zkontrolovat jejich hodnoty. (Můžete také použít **lokální** okna proměnných, které chcete sledovat, již existuje-li zkoumat hodnoty.)

1. Z **ladění** nabídce zvolte **Windows** > **Watch** > **kukátko 1**.

   **Kukátko 1** okno stane viditelnou.

2. Typ `$bookAverage` v **název** pole a potom stiskněte klávesu **Enter**.

   Hodnota `$bookAverage` proměnné zobrazí v **hodnotu** pole.

3. Na dalším řádku, zadejte `self::node()` v **název** pole a potom stiskněte klávesu **Enter**.

   `self::node()` je výraz XPath, který se vyhodnotí jako aktuální uzel kontextu. Hodnota `self::node()` výraz XPath je první uzel knihy. To změní, když jsme průběhu transformace.

4. Rozbalte `self::node()` uzel a potom rozbalte uzel kdo má hodnotu `price`.

   ![Okno kukátka během ladění XSLT v sadě Visual Studio](media/xslt-debugging-watch-window.png)

   Můžete zobrazit hodnotu cenu knih pro aktuální uzel knihy a porovnat `$bookAverage` hodnotu. Vzhledem k tomu knihy cena je nižší než průměr, `xsl:if` podmínka by být úspěšné při pokračování ladění procesu.

## <a name="step-through-the-code"></a>Krokovat kód

1. Stisknutím klávesy **F5** pokračujte.

   Protože splněna první uzel knihy `xsl:if` podmínka, uzel kniha je přidána do *níže average.xml* výstupního souboru. Ladicí program pokračuje v provádění, dokud je znovu umístěn na `xsl:if` element v šabloně stylů. Ladicí program je teď umístěný na druhém uzlu adresáře v *books.xml* souboru.

   V **kukátko 1** okno, `self::node()` hodnota nezmění na druhý uzel knihy. Prozkoumáním hodnota elementu cena můžete určit, že cena je vyšší než průměr, tedy `xsl:if` podmínka by selhat.

2. Stisknutím klávesy **F5** pokračujte.

   Protože druhý uzel knihy nesplňuje `xsl:if` podmínku, uzel knihy není přidán do *níže average.xml* výstupního souboru. Ladicí program pokračuje v provádění, dokud je znovu umístěn na `xsl:if` element v šabloně stylů. Ladicí program je nyní umístěn na třetí `book` uzlu *books.xml* souboru.

   V **kukátko 1** okno, `self::node()` hodnota nezmění na třetí uzel knihy. Porovnáním hodnoty `price` element, můžete určit, že cena je nižší než průměr. `xsl:if` Podmínku uspěli.

3. Stisknutím klávesy **F5** pokračujte.

   Vzhledem k tomu, `xsl:if` byla splněna podmínka, třetí kniha je přidána do *níže average.xml* výstupní soubor. Byly zpracovány všechny knihy v dokumentu XML a ladicí program se zastaví.

## <a name="sample-files"></a>Ukázkové soubory

Následující dva soubory jsou používány návodu.

### <a name="below-averagexsl"></a>below-average.xsl

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
        <xsl:if test="price &lt; $bookAverage">
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