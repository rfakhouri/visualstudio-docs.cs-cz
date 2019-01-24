---
title: Možnosti, textový editor, všechny jazyky, karty
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.All_Languages.Tabs
- VS.ToolsOptionsPages.Text_Editor.Basic.Tabs
- VS.ToolsOptionsPages.Text_Editor.CSharp.Tabs
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Tabs
- VS.ToolsOptionsPages.Text_Editor.CoffeeScript.Tabs
- VS.ToolsOptionsPages.Text_Editor.CSS.Tabs
- VS.ToolsOptionsPages.Text_Editor.Dockerfile.Tabs
- VS.ToolsOptionsPages.Text_Editor.F%2523.Tabs
- VS.ToolsOptionsPages.Text_Editor.HQL.Tabs
- VS.ToolsOptionsPages.Text_Editor.HTML.Tabs
- VS.ToolsOptionsPages.Text_Editor.HTMLX.Tabs
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Tabs
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Tabs
- VS.ToolsOptionsPages.Text_Editor.JSON.Tabs
- VS.ToolsOptionsPages.Text_Editor.LESS.Tabs
- VS.ToolsOptionsPages.Text_Editor.Plain_Text.Tabs
- VS.ToolsOptionsPages.Text_Editor.ResJSON.Tabs
- VS.ToolsOptionsPages.Text_Editor.SCSS.Tabs
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Tabs
- VS.ToolsOptionsPages.Text_Editor.StreamAnalytics.Tabs
- VS.ToolsOptionsPages.Text_Editor.T-SQL90.Tabs
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Tabs
- VS.ToolsOptionsPages.Text_Editor.XAML.Tabs
- VS.ToolsOptionsPages.Text_Editor.XML.Tabs
helpviewer_keywords:
- indents, Code Editor
- Code Editor, default behavior
- tabs, setting in Code Editor
- All Languages Text Editor Options dialog box
- editors, Code Editor
- Code Editor, indenting
- Code Editor, tabs
ms.assetid: 7e208e1d-5e3a-4bf7-a27b-4417e3e049c7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1923211a880956636570cd34fcabf876ee1f0055
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54785364"
---
# <a name="options-text-editor-all-languages-tabs"></a>Možnosti, textový editor, všechny jazyky, karty

Toto dialogové okno umožňuje změnit výchozí chování editoru kódu. Tato nastavení platí také pro jiné editory založen na editoru kódu, jako je HTML návrháře zobrazení zdroje. Chcete-li zobrazit tyto možnosti, vyberte **možnosti** z **nástroje** nabídky. V rámci **textový Editor** rozbalte složku **všechny jazyky** podsložku a klikněte na tlačítko **karty**.

> [!CAUTION]
> Tato stránka nastaví výchozí možnosti pro všechny vývojářské jazyky. Mějte na paměti, že obnovení možnost v tomto dialogovém okně obnovíte možnosti karty ve všech jazycích k jakékoli volby jsou tady vyberete. Chcete-li změnit možnosti textového editoru pro právě jeden jazyk, rozbalte podsložku pro daný jazyk a vyberte jeho možnosti.

Pokud vyberete různá nastavení na stránkách možností karty pro konkrétní programovací jazyky a pak zprávy "Nastavení odsazení pro jednotlivé textové formáty jsou v konfliktu mezi sebou", zobrazí se pro lišící se **Indenting**možnosti; a zobrazí se zpráva "Nastavení tabulátoru pro jednotlivé textové formáty jsou v konfliktu mezi sebou," pro lišící se **kartu** možnosti. Například toto připomenutí se zobrazí v případě **inteligentní odsazení** vybrána možnost Visual Basic, ale **blokovat odsazení** je vybrán pro Visual C++.

## <a name="indenting"></a>Odsazení

Žádná

Při výběru, nejsou nové řádky odsazeny. Kurzor je umístěn v prvním sloupci nový řádek.

Blok

Při výběru nového řádku mají být automaticky odsazeny. Kurzor je umístěn na stejné počáteční bod na každém řádku.

Smart

Pokud je vybráno, jsou umístěny nové řádky podle kontextu kód za další formátování nastavení a zásady technologie IntelliSense pro vývojový jazyk kódu. Tato možnost není k dispozici pro všechny vývojářské jazyky.

Například řádků uzavřeny mezi levá složená závorka ({}) a pravou závorkou (}) může být automaticky další zarážku od pozice zarovnané složené závorky odsazeny.

## <a name="tabs"></a>Karty

Velikost tabulátoru

Nastaví zastaví vzdálenost v mezery mezi kartu. Výchozí hodnota je mezery čtyři.

Velikost odsazení

Nastaví velikost v prostorách Automatické odsazení. Výchozí hodnota je mezery čtyři. Karta znaky a znaky se vloží tak, aby vyplnil zadané velikosti.

Vložit mezery

Pokud je vybráno, operace odsazení vložit pouze znaky mezery, tabulátory není. Pokud **velikost odsazení** je nastavena na 5, například pak pět znaky mezery jsou vloženy pokaždé, když stisknete klávesu TAB nebo **zvětšit odsazení** tlačítko **formátování** panel nástrojů.

Zachovat tabulátory

Pokud je vybráno, operace odsazení vložit tolik znaků TABULÁTORU nejvíce. Každý znak TABULÁTORU vyplní počet mezer podle **Velikost tabulátoru**. Pokud **velikost odsazení** není i násobek **Velikost tabulátoru**, znaky mezery jsou přidány k vyplnění rozdíl.

## <a name="see-also"></a>Viz také:

- [Možnosti, Textový editor, Všechny jazyky](../../ide/reference/options-text-editor-all-languages.md)
- [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)