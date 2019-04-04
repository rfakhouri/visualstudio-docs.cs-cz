---
title: Úvod do úprav pro vývojáře v JavaScriptu
description: Tento úvod do editoru kódu v sadě Visual Studio jsou uvedeny některé ze způsobů, že sada Visual Studio provádí zápis, procházení a porozumění kódu JavaScript jednodušší.
ms.date: 12/13/2018
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 111100038817d16d4655271f648aeb076bf1e9af
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856629"
---
# <a name="learn-to-use-the-code-editor"></a>Zjistěte, jak pomocí editoru kódu

V tomto stručný úvod do editoru kódu v sadě Visual Studio podíváme na některé ze způsobů, že sada Visual Studio provádí zápis, procházení a porozumění kódu jednodušší.

> [!TIP]
> Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/) stránku a nainstalovat zdarma. V závislosti na typu vývoj aplikací, které vám to jde, budete muset nainstalovat **úlohy pro vývoj Node.js** pomocí sady Visual Studio.

Tento článek předpokládá, že jste již obeznámeni s vývojem pro JavaScript. Pokud si nejste, doporučujeme vám podívejte se na kurz jako [vytvoření aplikace Node.js a Express](../javascript/tutorial-nodejs.md) první.

## <a name="add-a-new-project-file"></a>Přidejte nový soubor projektu

Integrované vývojové prostředí můžete přidat nové soubory do projektu.

1. S svůj projekt otevřít v sadě Visual Studio, klikněte pravým tlačítkem na složku nebo uzel projektu v Průzkumníku řešení (pravé podokno) a zvolte **přidat** > **nová položka**.

1. V **nový soubor** dialogovém okně **Obecné** kategorii, vyberte typ souboru, který chcete přidat, jako například **soubor JavaScript**a klikněte na tlačítko **otevřít** .

    Přidá nový soubor do projektu a otevře v editoru.

## <a name="use-intellisense-to-complete-words"></a>K dokončení slova použít technologie IntelliSense

Technologie IntelliSense je neocenitelný při řízení prostředků, když jste psaní kódu. Může zobrazit informace o Dostupní členové typu nebo parametr podrobnosti pro jiné přetížení metody. V následujícím kódu, když zadáte `Router()`, naleznete v tématu typy argumentů, které můžete předat. Tomu se říká Nápověda k podpisu.

![Používání technologie IntelliSense](../javascript/media/write-code-signature-checking.png)

K dokončení slova Jakmile zadáte dostatečný počet znaků k rozlišení ho můžete také použít technologie IntelliSense. Pokud umístíte kurzor po `data` řetězec v následujícím kódu a typ `get`, technologie IntelliSense zobrazí funkce definované výše v kódu nebo definované v knihovny třetí strany, který jste přidali do svého projektu.

![Používání technologie IntelliSense](../javascript/media/write-code-intellisense.png)

Technologie IntelliSense může také zobrazit informace o typech při najetí myší programovací prvky.

K poskytování informací technologie IntelliSense, můžete použít službu jazyka TypeScript *d.ts* soubory a komentářích JSDoc. U většiny běžných knihoven jazyka JavaScript *d.ts* soubory byly automaticky získány. Další informace o tom, jak získat informace technologie IntelliSense, viz [technologie IntelliSense jazyka JavaScript](../ide/javascript-intellisense.md?toc=/visualstudio/javascript/toc.json)

## <a name="check-syntax"></a>Zkontrolovat syntaxi

Služba jazyka používá ESLint pro zajištění kontroly syntaxe a linting. Pokud je potřeba nastavit možnosti pro kontrolu syntaxe v editoru vyberte **nástroje** > **možnosti** > **JavaScript/TypeScript**  >  **Linting**. Možnosti linting odkazovat na globální ESLint konfigurační soubor.

V následujícím kódu uvidíte zelené zvýraznění (zelenou vlnovkou) na výraz syntaxe. Najeďte myší zvýraznění syntaxe.

![Chyba syntaxe zobrazení](../javascript/media/write-code-syntax-checking.png)

Poslední řádek této zprávě se říká, že služba jazyka očekávala se čárka (`,`). Zelená vlnovku zobrazuje varování. Červenou vlnovkou indikaci chyby.

Ve spodní části podokna klikněte **seznam chyb** kartu pro zobrazení upozornění a popis a název souboru a řádku počty.

![Zobrazení seznamu chyb](../javascript/media/write-code-error-list.png)

Tento kód můžete opravit přidáním čárky (`,`) před `"data"`.

## <a name="comment-out-code"></a>Okomentujte kód

Panel nástrojů, který je řádek tlačítek v panelu nabídek v sadě Visual Studio může pomoct zvýší vaši produktivitu při kódování. Například můžete přepnout režim dokončování IntelliSense ([IntelliSense](../ide/using-intellisense.md) je kódování podpory, který zobrazí seznam odpovídajících metod, mimo jiné), zvětšit nebo zmenšit odsazení řádku nebo okomentujte kód, který nechcete kompilace. V této části jsme vám okomentujte nějaký kód.

Vyberte jeden nebo více řádků kódu v editoru a pak klikněte **Odkomentujte vybrané řádky** tlačítko ![Odkomentujte tlačítko](../javascript/media/write-code-comment-out.png) na panelu nástrojů. Pokud chcete použít klávesnici, stiskněte **Ctrl**+**K**, **Ctrl**+**C**.

Znaky komentáře JavaScript `//` jsou přidány do začátku okomentujte kód každém řádku.

## <a name="collapse-code-blocks"></a>Sbalit bloky kódu

Pokud je potřeba zpřehlednit zobrazení některých oblastech kódu, můžete sbalit. Vyberte malé šedé pole se znaménkem minus uvnitř u okraje řádku první funkce. Nebo, pokud jste uživatel klávesnice, umístěte kurzor kdekoli v konstruktoru kód a stiskněte klávesu **Ctrl**+**M**, **Ctrl**+**M** .

![Sbalování tlačítko Sbalit](../javascript/media/write-code-collapse-code.png)

Sbalí blok kódu pouze na první řádek, následované třemi tečkami (`...`). Rozbalte blok kódu znovu, klikněte na stejnou šedé pole, které teď má znaménko plus nebo stisknutím klávesy **Ctrl**+**M**, **Ctrl**+**M**  znovu. Tato funkce se nazývá [Osnova](../ide/outlining.md) a je zvláště užitečné, když jste sbalení dlouhé funkce nebo celé třídy.

## <a name="view-definitions"></a>Definice zobrazení

Editor sady Visual Studio usnadňuje Zkontrolujte definici typu, funkce atd. Jedním ze způsobů, je přejít na soubor, který obsahuje definici, například výběrem **přejít k definici** kdekoli programovací element odkazuje. Ještě rychlejší tak, aby váš výběr čárka nepohybuje mimo soubor pracujete v je použití [definice operace Peek](../ide/go-to-and-peek-definition.md#peek-definition). Umožňuje zobrazení náhledu definice `render` metodu v následujícím příkladu.

Klikněte pravým tlačítkem na `render` a zvolte **definice operace Peek** z nabídky obsahu. Také můžete stisknout klávesu **Alt**+**F12**.

   Se zobrazí automaticky otevírané okno s definicí `render` metody. V automaticky otevíraném okně, nebo dokonce náhled definice jiného typu než peeked kódu můžete posouvat.

   ![Okno definice operace Peek](../javascript/media/write-code-peek-definition.png)

Zavřete okno Definice nahlédnout do malé pole "x" v pravé horní části v automaticky otevíraném okně výběrem.

## <a name="use-code-snippets"></a>Používání fragmentů kódu

Visual Studio poskytuje užitečné *fragmenty kódu* , že vám pomůže rychle a snadno generovat běžně používá bloky kódu. [Fragmenty kódu](../ide/code-snippets.md) jsou k dispozici pro různé programovací jazyky, včetně jazyka JavaScript. Přidejme `for` smyčky do souboru kódu.

Umístěte ukazatel myši, ve které chcete vložit fragment kódu, klikněte pravým tlačítkem a zvolte **fragment** > **Vložit fragment**.

![Fragment kódu v sadě Visual Studio](../javascript/media/write-code-insert-snippet.png)

**Vložit fragment** pole se zobrazí v editoru. Zvolte **Obecné** a potom dvakrát klikněte **pro** položku v seznamu.

![Fragment kódu pro smyčky for v sadě Visual Studio](../javascript/media/write-code-insert-snippet-for-loop.png)

Tím se přidá `for` smyčky fragment kódu:

```javascript
for (var i = 0; i < length; i++) {

}
```

Můžete si prohlédnout fragmenty kódu k dispozici pro váš jazyk výběrem **upravit** > **IntelliSense** > **Vložit fragment**a pak Výběr složky váš jazyk.

## <a name="see-also"></a>Viz také:

- [Fragmenty kódu](../ide/code-snippets.md)
- [Vyhledání kódu](../ide/navigating-code.md)
- [Sbalování](../ide/outlining.md)
- [Přejít k definici a náhled definice](../ide/go-to-and-peek-definition.md)
- [Refaktoring](../ide/refactoring-in-visual-studio.md)
- [Používání technologie IntelliSense](../ide/using-intellisense.md)
