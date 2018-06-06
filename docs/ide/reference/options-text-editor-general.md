---
title: Možnosti, textový editor, obecné
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.TOOLSOPTIONSPAGES.TEXT_EDITOR.SQL_SERVER_TOOLS.GENERAL
- VS.ToolsOptionsPages.Text_Editor.All_Languages.General
- VS.ToolsOptionsPages.Text_Editor.RDL_Expression.General
- VS.ToolsOptionsPages.Text_Editor.SQL.General
- vs.toolsoptionspages.text_editor
- VS.ToolsOptionsPages.Text_Editor.XML.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL80.General
- VS.ToolsOptionsPages.Text_Editor.CSS
- VS.ToolsOptionsPages.Text_Editor.Plain_Text.General
- VS.ToolsOptionsPages.Text_Editor.SQL_Script.General
- VS.ToolsOptionsPages.Text_Editor.CSharp.General
- VS.ToolsOptionsPages.Text_Editor.All_Languages
- VS.ToolsOptionsPages.Text_Editor.T-SQL7.General
- VS.ToolsOptionsPages.Text_Editor.Basic.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL.General
- VS.ToolsOptionsPages.Text_Editor.F#.Tabs
- VS.ToolsOptionsPages.Text_Editor.F#
- VS.ToolsOptionsPages.Text_Editor.PL/SQL.General
- VS.ToolsOptionsPages.Text_Editor.C/C++.General
- VS.ToolsOptionsPages.Text_Editor.Plain_Text
- VS.ToolsOptionsPages.Text_Editor.HTML
- VS.ToolsOptionsPages.Text_Editor.XAML.General
- VS.ToolsOptionsPages.Text_Editor
- VS.ToolsOptionsPages.Text_Editor.F#.General
- VS.ToolsOptionsPages.Text_Editor.XOML.General
- VS.ToolsOptionsPages.Text_Editor.SQL
- vs.toolsoptionspages.text_editor.c/c++
- VS.ToolsOptionsPages.Text_Editor.SQL_Script
- VS.ToolsOptionsPages.Text_Editor.T-SQL90.General
- VS.ToolsOptionsPages.Text_Editor.General
- VS.ToolsOptionsPages.Text_Editor.CSharp
- VS.ToolsOptionsPages.Text_Editor.Python
- VS.ToolsOptionsPages.Text_Editor.R
helpviewer_keywords:
- Text Editor Options dialog box
- Code Editor
- Text Editor [Visual Studio]
- editors, global settings
ms.assetid: 4ac21e48-3243-4141-9058-7eaf12b3cde7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a3296ec07194f1815b819f69cf97224be50368f
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747812"
---
# <a name="options-text-editor-general"></a>Možnosti, textový editor, obecné

Toto dialogové okno umožňuje měnit globální nastavení pro Visual Studio editoru kódu a text. K zobrazení tohoto dialogového okna, vyberte **možnosti** na **nástroje** nabídky, rozbalte **textového editoru** složku a potom vyberte **Obecné**.

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="settings"></a>Nastavení

### <a name="drag-and-drop-text-editing"></a>Přetáhnout myší úpravy textu

Pokud vybraná, umožňuje přesunout text tak, že ho vyberete a jeho přetažením pomocí myši do jiného umístění v aktuálním dokumentu nebo jiného dokumentu otevřít.

### <a name="automatic-delimiter-highlighting"></a>Zvýraznění automatické oddělovač

Při výběru zvýraznění oddělovač znaků, které oddělují parametry nebo párů hodnot položky, jakož i odpovídající složené závorky.

### <a name="track-changes"></a>Sledování změn

Pokud je vybraná editoru kódu, se zobrazí žlutý svislice v výběr okraje označit kódu, které se změnily od naposledy uložení. Při ukládání změny stát zelená svislé čáry.

### <a name="auto-detect-utf-8-encoding-without-signature"></a>Automaticky rozpoznat bez podpisu kódování UTF-8

Ve výchozím nastavení zjistí editoru kódování vyhledáním značky pořadí bajtů nebo charset značky. Pokud ani jeden z nich je nalezena v aktuálním dokumentu, pokusí se editoru kódu automatické rozpoznání naskenováním pořadí bajtů kódování UTF-8. Chcete-li zakázat automatické zjišťování kódování, zrušte tuto možnost.

## <a name="display"></a>Displej

### <a name="selection-margin"></a>Výběr okraje

Když vyberete, zobrazí svislý okraj podél levého okraje editoru textová oblast. Můžete kliknout na toto rozpětí celý řádek textu, vyberte nebo klikněte na tlačítko a přetáhněte ji vybrat po sobě jdoucích řádků textu.

|Výběr okraje na|Výběr okraje vypnuto|
|-------------------------|--------------------------|
|![HTMLpageSelectionMarginOn – snímek obrazovky](../../ide/reference/media/vxselmaron.gif)|![HTMLpageSelectionMarginOff – snímek obrazovky](../../ide/reference/media/vxselmaroff.gif)|

### <a name="indicator-margin"></a>Okraj indikátoru

Když vyberete, zobrazí svislý okraj mimo podle levé hrany editoru textová oblast. Po kliknutí na toto rozpětí, zobrazí ikonu a popis tlačítka, která se vztahují na text. Například bod přerušení nebo úloh zástupce seznamu zobrazit v indikátoru okraj. Indikátor okraj informace ne k tisku.

### <a name="vertical-scroll-bar"></a>Svislý posuvník

Když vyberete, zobrazí svislý posuvník, které umožňuje nahoru a dolů přejděte do zobrazení prvků, které spadají mimo oblast zobrazení editoru. Pokud svislé posuvníky nejsou k dispozici, můžete Page Up Page Down a klíče kurzoru přejděte.

### <a name="horizontal-scroll-bar"></a>Vodorovného posuvníku

Když vyberete, zobrazí vodorovný posuvník, které umožňuje ze strany na stranu přejděte do zobrazení prvků, které spadají mimo oblast zobrazení editoru. Pokud vodorovné posuvníky jsou k dispozici, můžete posuňte ukazatel klíče.

### <a name="highlight-current-line"></a>Zvýraznění aktuálního řádku

Když vyberete, zobrazí šedé pole kolem řádek kódu, ve kterém se nachází kurzor.

## <a name="see-also"></a>Viz také:

- [Možnosti, textový Editor, všechny jazyky](../../ide/reference/options-text-editor-all-languages.md)
- [Možnosti, textový Editor, všechny jazyky, karty](../../ide/reference/options-text-editor-all-languages-tabs.md)
- [Možnosti, textový Editor, přípona souboru](../../ide/reference/options-text-editor-file-extension.md)
- [Identifikování a přizpůsobení klávesových zkratek](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)
- [Vlastní nastavení editoru](../../ide/customizing-the-editor.md)
- [Používání atributu IntelliSense](../../ide/using-intellisense.md)