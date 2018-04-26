---
title: Přidání podpory editoru Visual Studio pro jiné jazyky
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- syntax colorization
- IntelliSense
- IDE, navigation
- documents [Visual Studio], navigation
- TextMate bundle
- TextMate language grammar
- language support
ms.assetid: d78c43ee-4ef2-42e5-984e-d137de4e7e92
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: ae9b9dcbed2886344ab8e81932dbd7ad03adfa1f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="adding-visual-studio-editor-support-for-other-languages"></a>Přidání podpory editoru Visual Studio pro jiné jazyky
Další informace o tom, jak editoru Visual Studio podporuje čtení a procházení jazyky jiný počítač a jak můžete přidat podporu editoru Visual Studio pro jiné jazyky.

## <a name="syntax-colorization-statement-completion-and-navigate-to-support"></a>Zabarvení syntaxe, dokončování a přejít na podporu
 Funkce v editoru Visual Studio například zabarvení syntaxe, dokončování a přejít na vám může pomoct další snadno číst, vytvářet a upravovat kód. Následující snímek obrazovky ukazuje příklad úpravy skript Perl v sadě Visual Studio. Syntaxe je automaticky obarvené. Například poznámky v kódu, se zobrazí zeleně, je kód černé, cest red a příkazy jsou modré. Editoru Visual Studio automaticky použije zabarvení syntaxe pro žádný jazyk, kterou podporuje. Kromě toho, abyste před zahájením zadejte známé jazyk – klíčové slovo nebo objekt, dokončování zobrazí seznam možných příkazy a objektů. Dokončování příkazů můžete vytvořit kód více snadno a rychle.

 ![Zabarvení syntaxe ve skriptu Perl](../ide/media/vside_perledit.png "VSIDE_PerlEdit")

 Visual Studio teď poskytuje, zabarvení syntaxe a základní dokončování podporu pro následující jazyky pomocí [TextMate gramatika](https://manual.macromates.com/en/language_grammars). Pokud váš oblíbený jazyk není v tabulce, ale Nebojte – můžete ho přidat.

|||||||
|-|-|-|-|-|-|
|A. bat|F#|Java|Markdownu|Rzivosti|Visual Basic|
|Clojure|Přejděte|JavaDoc|Jazyka Objective-C|ShaderLab|C#|
|CMake|Groovy|FORMÁT JSON|Perl|ShellScript|Visual C++|
|CoffeeScript|HTML|MENŠÍ|Python|SQL|VBNet|
|CSS|INI|LUA|R|Kód SWIFT|XML|
|Docker|Jade|Ujistěte se|Ruby|TypeScript|YAML|

 Kromě zabarvení syntaxe a dokončování basic, Visual Studio má taky funkci [přejít na](https://blogs.msdn.microsoft.com/benwilli/2015/04/09/visual-studio-tip-3-use-navigate-to/). Tato funkce umožňuje rychle vyhledat soubory kódu, cesty k souborům a kód symboly. Visual Studio poskytuje přejít na podporu pro následující jazyky.

-   Přejděte

-   Java

-   JavaScript

-   PHP

-   TypeScript

-   Visual Basic

-   Visual C++

-   C#

Všechny tyto typy souborů mají funkce popsané dříve i když podpora pro daný jazyk ještě nebyl nainstalován. Instalace specializované podpory pro některé jazyky může poskytnout další jazyková podpora, jako je například IntelliSense nebo jiné pokročilé jazykové funkce jako je například žárovek.

## <a name="adding-support-for-non-supported-languages"></a>Přidání podpory pro nepodporované jazyky
 Visual Studio 2015 Update 1 a novější verze podporují jazyk v editoru pomocí [TextMate gramatika](https://manual.macromates.com/en/language_grammars). Pokud vaše oblíbené programovací jazyk není aktuálně podporován v editoru Visual Studio, nejprve hledat na webu – sady TextMate pro jazyk možná již existuje. Pokud nemůžete najít jeden, ale můžete přidat podporu pro něj sami ve Visual Studiu 2015 Update 1 nebo novější vytvořením sady model TextMate gramatika jazyka a fragmenty kódu.

 Přidejte všechny nové gramatika TextMate pro sadu Visual Studio v následující složce:

 *%userprofile%\\.vs\Extensions*

 Tento základní cestě přidejte následující složkám, pokud se vztahují na vaši situaci:

|Název složky|Popis|
|-----------------|-----------------|
|\\*\<název jazyka >*|Jazykovou složku. Nahraďte  *\<název jazyka >* s názvem jazyka. Například *\Matlab*.|
|*\Syntaxes*|Gramatika složka. Obsahuje gramatiky *.json* soubory pro daný jazyk, jako například *Matlab.json*.|
|*\Snippets*|Fragmenty kódu složka. Obsahuje fragmenty kódu pro jazyk.|

 V systému Windows *% userprofile %* přeloží cestu: *c:\Users\\\<uživatelské jméno >*. Pokud v systému neexistuje složky rozšíření, musíte se k jeho vytvoření. Pokud daná složka již existuje, bude ho skrytá.

 Podrobnosti o tom, jak vytvořit TextMate gramatika najdete v tématu [TextMate – Úvod do gramatika jazyka: vložené tom, jak přidat zvýraznění syntaxe zdrojového kódu ve formátu HTML](https://developmentality.wordpress.com/2011/02/08/textmate-introduction-to-language-grammars/) a [poznámky o tom, jak vytvořit gramatika jazyka a vlastní Motiv pro sady Textmate](https://benparizek.com/notebook/notes-on-how-to-create-a-language-grammar-and-custom-theme-for-a-textmate-bundle).

## <a name="see-also"></a>Viz také

- [Visual Studio 2013 přejděte na vylepšení](https://blogs.msdn.microsoft.com/mvpawardprogram/2013/10/22/visual-studio-2013-navigate-to-improvements/)
- [Návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md)
- [Návod: Zobrazení dokončování příkazů](../extensibility/walkthrough-displaying-statement-completion.md)