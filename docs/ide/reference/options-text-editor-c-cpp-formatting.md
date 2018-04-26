---
title: Možnosti, textový editor, C/C++, formátování
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.C%2fC%2b%2b.Formatting.General
dev_langs:
- CPP
helpviewer_keywords:
- Text Editor Options dialog box, formatting
ms.assetid: cb6f1cbb-5305-48da-a8e8-33fd70775d46
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 913413b4178a087c524ef26173fcbcc8c1d8b09b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="options-text-editor-cc-formatting"></a>Možnosti, textový editor, C/C++, formátování
Umožňuje změnit výchozí chování editoru kódu při programování v jazyce C nebo C++.

 Pro přístup k této stránce v **možnosti** dialogové okno, v levém podokně rozbalte **textového editoru**, rozbalte položku **C/C++** a potom klikněte na **formátování** .

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).


## <a name="cc-options"></a>Možnost jazyka C/C++
 **Povolit automatické rychlé informace popisy tlačítek**

 Povolí nebo zakáže funkci Rychlé informace technologie IntelliSense.

## <a name="inactive-code"></a>Neaktivní kód
 **Zobrazit bloky neaktivní kódu**

 Kód, který je neaktivní kvůli `#ifdef` deklarace jsou obarvené jinak k vám pomůže ho rozpoznat.

 **Zakázat krytí neaktivní kódu**

 Neaktivní kód lze poznat pomocí barvy místo průhlednosti.

 **Procento krytí neaktivní kódu**

 Stupeň průhlednosti bloků neaktivního kódu lze přizpůsobit.

## <a name="indentation"></a>Odsazení
 **Odsazení složené závorky**

 Můžete nakonfigurovat způsob zarovnání složené závorky po stisknutí klávesy ENTER po zahájení bloku kódu, například funkci nebo `for` smyčky. Složené závorky mohou být buď zarovnány k prvnímu znaku bloku kódu, nebo odsazeny.

 **Automatické odsazení na kartě**

 Můžete nastavit, co se stane s aktuálním řádkem kódu po stisknutí klávesy TAB. Buď se odsadí řádek, nebo se vloží tabulátor.

## <a name="miscellaneous"></a>Různé
 **Zobrazení výčtu komentáře v okně Seznam úloh**

 Editor může v otevřených zdrojových souborech vyhledat přednastavená slova v komentářích. Vytvoří položku v **seznam úkolů** okna pro všechny klíčová slova, která najde.

 **Zvýraznění odpovídající tokeny**

 Když je kurzor vedle složené závorky, může editor zvýraznit protější složenou závorku, abyste snadněji viděli obsažený kód.

## <a name="outlining"></a>Sbalování
 **Zadejte popisující režimu při otevírání souborů**

 Když v textovém editoru otevřete soubor, můžete povolit funkci sbalování. Další informace najdete v tématu [Osnova](../../ide/outlining.md). Při výběru této možnosti se funkce sbalování povolí při otevření souboru.

 **Automatické sbalení #pragma oblast bloků**

 Pokud tato možnost je vybrané, automatické osnovy pro [direktivy pragma](/cpp/preprocessor/pragma-directives-and-the-pragma-keyword) je povoleno. V režimu sbalování tak můžete rozbalit nebo sbalit bloky pragma region.

 **Automatické sbalení blok příkazu**

 Při výběru této možnosti je povoleno automatické sbalování následujících příkazových konstrukcí:

-   [if-else](/dotnet/csharp/language-reference/keywords/if-else)

-   [switch – příkaz (C++)](/cpp/cpp/switch-statement-cpp)

-   [while – příkaz (C++)](/cpp/cpp/while-statement-cpp)

## <a name="see-also"></a>Viz také

- [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)
- [Používání atributu IntelliSense](../../ide/using-intellisense.md)