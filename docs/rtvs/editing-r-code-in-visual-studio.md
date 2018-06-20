---
title: Úpravy kódu jazyka R
description: Visual Studio nabízí šité na míru úpravy prostředí R a přitom zachovat všechny funkce a umožňuje používat rozšíření.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 9eef75c505cb3ed41e24f99e08468512e424884a
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238333"
---
# <a name="edit-r-code-in-visual-studio"></a>Upravit kód R v sadě Visual Studio

R nástrojů pro Visual Studio (RTVS) přizpůsobuje jim úpravy speciálně pro R a přitom zachovat všechny funkce a umožňuje používat rozšíření sady Visual Studio. (Například pokud dáváte přednost vazeb klíče VIM, můžete nainstalovat bezplatnou [VsVim rozšíření](https://visualstudiogallery.msdn.microsoft.com/59ca71b3-a4a3-46ca-8fe1-0e90e3f79329) z Galerie sady Visual Studio.)

Kromě funkcí v tomto článku také vidět [IntelliSense](r-intellisense.md), [linting](linting-r-code.md), [výstřižky kódu](code-snippets-for-r.md), a [R Markdownu](rmarkdown-with-r-in-visual-studio.md).

## <a name="syntax-highlighting"></a>zvýraznění syntaxe

Kromě zvýrazňování různé části kódu, například řetězce, komentáře a klíčová slova, RTVS také označuje a umožňuje odkazy v komentářích:

![Pro kód R zvýrazňování syntaxe](media/editing-syntax-colors.png)

Chcete-li přizpůsobit písmo a barvy určité zvýraznění, vyberte **nástroje** > **možnosti** příkaz, přejděte na **prostředí**  >  **Písma a barev**, pak změňte nastavení pro R související položky v **zobrazení položek** pole:

![Písma a barev možnosti kódu jazyka R](media/editing-syntax-colors-options.png)

Visual Studio také podtrhne chyby syntaxe v editoru:

![Chyba syntaxe zvýraznění v kódu jazyka R](media/editing-syntax-error.png)

Chcete-li toto chování změnit, **Upřesnit** > **kontrola syntaxe** nastavení v části [možností editoru](#editor-options).

## <a name="edit-and-organize-code"></a>Upravit a uspořádat kódu

Psaní kódu RTVS poskytuje automatické doplňování, jak je popsáno na [IntelliSense](r-intellisense.md) stránky. Zajišťuje také automatické formátování například dokončení složené závorky a závorky: 

![Animace vložené formátování](media/editing-inline-formatting.gif)

Při psaní volání funkce, které mají mnoho parametrů, často budete chtít rovině parametry, které usnadňují kód. RTVS pamatuje odsazení vaší sady parametrů a automaticky použije tento odsazení pro následující řádky:

![Animace automatického odsazení](media/editing-auto-indentation.gif)

Chcete-li toto chování změnit, [možností editoru](#editor-options) pro **karty** skupiny.

Sbalitelné kód oblasti umožňují dočasně skrýt součástí kódu v editoru. Visual Studio vytvoří různých oblastech pro vás automaticky, jako u Víceřádkový příkazy, pokud **Upřesnit** > **Osnova** > **osnova kódu**  je možnost nastavena na vypnuto.

K vytvoření požadované kód oblasti vlastní příkazu Obklopit s komentáři, které končí `---`. Malá +/-ovládací prvky nalevo od kódu umožňuje pak rozbalení a sbalení oblastí:

![Vytváření sbalitelné oblasti s komentáři](media/editing-collapsible-regions.gif)

Ve výchozím nastavení, Visual Studio vloží prostory po stisknutí klávesy **kartě** klíč. Toto chování lze znovu změnit, jak je popsáno na [možnosti, textový Editor, karty](../ide/reference/options-text-editor-all-languages.md).

## <a name="code-navigation"></a>Navigace v kódu

Navigace kódu umožňuje rychlý přístup ke zdrojovému kódu vašeho programu R a jeho knihoven. Tyto funkce umožňují toku práci už nemusíte ručně vyhledávání kódu.

**Přejít k definici** rychle skáče definice funkce nebo objeví zkrácená editoru vložené číst zdrojový kód funkce knihovny. Právě klikněte pravým tlačítkem na funkce, které vás zajímají, a vyberte **přejít k definici**, nebo umístěte kurzor do funkce a stiskněte klávesu **F12**.

Tento příkaz otevře nové okno editoru obsahující zdrojového kódu pro funkce. Kurzor je nastavený pohodlně na začátku v definici funkce.

**Funkce Náhled definice**, vyvolá se z místní nabídky nebo **Alt**+**F12**, vloží jen pro čtení, posouvatelného oblast, která obsahuje zdrojový kód níže uvedené funkce volání funkce:

![Animace pro funkce Náhled definice](media/editing-peek-definition.gif)

## <a name="send-code-to-the-interactive-window"></a>Poslat kód do interaktivních okna

Celá řada vývojářů jako napsat kód v editoru a poslat kódu [interaktivních okna](interactive-repl-for-r-in-visual-studio.md) pro okamžité testování (také označované jako čtení-vyhodnotit-tisk-smyčky nebo REPL). Stisknutím **Ctrl**+**Enter** v R odešle aktuálního řádku kódu do interaktivních okna editoru a pak umístí kurzor na další řádek. S **Ctrl**+**Enter**, potom můžete efektivně krokovat kódu z editoru.

Můžete také vybrat kód a stiskněte klávesu **Ctrl**+**Enter** použít celý výběr. Případně, klikněte pravým tlačítkem na výběr a vyberte **spouštět v interaktivní**.

## <a name="format-code"></a>Formátovat kód

Visual Studio automatické formátování udržuje kód, který napíšete, a také kód, který můžete vložit do editoru formátovaný jako sada podle vašich předvolbách. Můžete také vytvořit výběr, klikněte pravým tlačítkem a vyberte **výběr formátu** (**Ctrl**+**tisíc**,**F**) použít ty Předvolby. Například pokud jste měli definici funkce všechny na jeden řádek:

```R
f<-function  (a){  return(a + 1) }
```

Použití formátování vyčistí ho jako:

```R
f <- function(a) { return(a + 1) }
```

Chcete-li změnit formátování kódu celý soubor, vyberte **upravit** > **Upřesnit** > **formátovat dokument** (**Ctrl** + **E**,**D**).

Automatické formátování je samostatný operace, která lze vrátit zpět. Například pokud kódu vložíte do editoru a formátování se vztahuje, výběrem **upravit** > **vrátit zpět** nebo stiskněte **Ctrl** + **Z** jednou obrátí formátování; druhý **vrátit zpět** obrátí vložení sám sebe.

Možnosti formátování (včetně vypnutí formátování) jsou nastaveny prostřednictvím **nástroje** > **možnosti** na **textového editoru**  >  **R** > **Upřesnit** kartě. Můžete přejít přímo na tuto stránku pomocí buď **R nástroje** > **možností editoru** příkaz nebo nástrojem v editoru pravým tlačítkem a vyberete **možnostiformátování**. Najdete v článku [možností editoru](#editor-options) podrobnosti.

## <a name="inserting-roxygen-comments"></a>Vkládání Roxygen komentáře

RTVS poskytuje zástupce pro generování [Roxygen](http://roxygen.org/) komentáře pomocí názvů parametrů funkce. Stačí zadat `###` na prázdný řádek výše v definici funkce:

![Animace vložení Roxygen komentář](media/editing-roxygen-comments.gif)

## <a name="editor-options"></a>Možnosti editoru

Editor specifické možnosti se konfigurují pomocí **nástroje** > **možnosti** příkazu, přejdete na **textového editoru** > **R**, nebo použijte příkaz zástupce **R nástroje** > **možností editoru**.

Možnosti na **Obecné**, **posuvníky**, a **karty** karty nejsou specifické pro R, ale jsou místo obecné nastavení sady Visual Studio dostupné pro všechny jazyky, ale použitá na základ pro jazyk. Podrobnosti najdete v tématu v těchto článcích:

- [Možnosti, textový Editor, všechny jazyky](../ide/reference/options-text-editor-all-languages.md)
- [Sledování kódu můžete přizpůsobením posuvníku](../ide/how-to-track-your-code-by-customizing-the-scrollbar.md)
- [Možnosti, textový Editor, karty](../ide/reference/options-text-editor-all-languages-tabs.md)

Možnosti na **R** > **Upřesnit** kartě jsou specifické pro RTVS:

| Skupina | Možnost | Výchozí | Popis |
| --- | --- | --- | --- |
| Formátování | Automatické formátování | On | Přeformátuje kód při psaní. Nemá vliv **výběr formátu** nebo **formátovat dokument** příkazy. |
| | Rozšířené složené závorky | Off | Umístí otevřenou {na nový řádek. |
| | Formátování v vložení | On | Použije formátování na vložení. |
| | Formát oboru na} | On | Formáty rozsah po zadání uzavírající}. |
| | Místo za desetinnou čárkou | On | Umístí mezeru po čárkami. |
| | Prostor po – klíčové slovo | On | Umístí mezeru po klíčová slova jako `if`, `while`, a `repeat`. |
| | Místo před { | On | Umístí mezery před a otevírání {. |
| | Mezery okolo = | On | Umístí prostory znaménku rovná. |
| IntelliSense | Potvrdit na klávesy Enter | Off | Potvrdí výběr automatické dokončování při **Enter** stisknutí. |
| | Potvrdit na klíč místa | Off | Potvrdí výběr automatické dokončování při **místo** stisknutí.|
| | Seznam dokončení na první znak | On | Zobrazuje seznam dokončení v první typy znaků. Když vypnutý, zobrazí se seznam dokončení s **upravit** > **IntelliSense** > **vypsat členy** (**Ctrl** + **J**). |
| | Seznam dokončení na **kartě** klíč | Off | Vyvolá seznam dokončení zadáním jeden nebo více znaků a stisknutím klávesy **kartě**. |
| | Shoda částečně typy názvy argumentů | Off | Při psaní názvy argumentu ve volání funkce, podpis nápovědy se zobrazí popis argument, který je nejlepší shodu. |
| Interaktivní okno | Kontrola syntaxe v konzole R | Off | V okně interaktivní kontrola syntaxe se vztahuje. Kontrola syntaxe nemusí fungovat správně s více řádky příkazy. | 
| Sbalování | Osnova kódu | On | Automaticky vytvoří sbalitelné oblasti pro oblasti jako příkazy víceřádkový. |
| Kontrola syntaxe | Zobrazit chyby syntaxe | On | Umožňuje automatické syntaxe Kontrola kódu. |
