---
title: Možnosti, textový editor, obecné
ms.date: 01/18/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.RDL_Expression.General
- VS.ToolsOptionsPages.Text_Editor.SQL.General
- vs.toolsoptionspages.text_editor
- VS.ToolsOptionsPages.Text_Editor.T-SQL80.General
- VS.ToolsOptionsPages.Text_Editor.SQL_Script.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL7.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL.General
- VS.ToolsOptionsPages.Text_Editor.PL/SQL.General
- VS.ToolsOptionsPages.Text_Editor
- VS.ToolsOptionsPages.Text_Editor.XOML.General
- VS.ToolsOptionsPages.Text_Editor.SQL
- VS.ToolsOptionsPages.Text_Editor.SQL_Script
- VS.ToolsOptionsPages.Text_Editor.General
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9a7bcf7b57c6cdc7e0ff4ff5a851397b7c96b345
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55930230"
---
# <a name="options-text-editor-general"></a>Možnosti, textový editor, obecné

Toto dialogové okno umožňuje měnit globální nastavení pro kód a text editoru sady Visual Studio. Chcete-li zobrazit toto dialogové okno, vyberte **možnosti** na **nástroje** nabídky, rozbalte **textový Editor** složku a pak vyberte **Obecné**.

## <a name="settings"></a>Nastavení

### <a name="drag-and-drop-text-editing"></a>Přetáhnout myší úpravy textu

Při výběru, umožňuje přesunout text jeho výběrem a přetažením myší do jiného umístění v rámci aktuálního dokumentu nebo libovolného otevřeného dokumentu.

### <a name="automatic-delimiter-highlighting"></a>Automatické zvýrazňování oddělovače

Pokud je vybráno, jsou zvýrazněny znaky oddělovače, které oddělují parametry nebo párů hodnot položky, jakož i odpovídající složené závorky.

### <a name="track-changes"></a>Sledování změn

Pokud je vybrána editoru kódu, se zobrazí v okraj výběru označit kód, který se změnil, protože soubor byl uložen jako poslední svislé Žlutá čára. Při ukládání změn budou zelené svislé čáry.

### <a name="auto-detect-utf-8-encoding-without-signature"></a>Automatické rozpoznání kódování UTF-8 bez podpisu

Ve výchozím nastavení zjistí editoru kódování tak, že značky pořadí bajtů nebo znaková sada značky. Pokud ani jedno nenajde v aktuálním dokumentu, pokusí se editor kódu tím, že kontroluje pořadí bajtů kódování automatické rozpoznání kódování UTF-8. Chcete-li zakázat automatickou detekcí kódování, zrušte zaškrtnutí tohoto políčka.

### <a name="follow-project-coding-conventions"></a>Podle konvence psaní kódu projektu

Při výběru konvence kódování zadaného projektu přepsat všechny konvence kódování, které používáte na svých osobních projektech.

### <a name="enable-mouse-click-to-perform-go-to-definition"></a>Povolit pro kliknutí myši provedení příkazu Přejít k definici

Při výběru stisknete klávesu **Ctrl** a podržte ukazatel myši nad prvek při kliknutí myší. Tím přejdete na definici vybraného prvku. Můžete také zvolit **Alt** nebo **Ctrl** + **Alt** z **použít modifikátor klíč** rozevíracího seznamu.

Vyberte **Otevřít definici v zobrazení náhledu** zaškrtnutím políčka Zobrazit definice prvku v okně bez navigaci pryč z aktuální umístění v editoru kódu.

## <a name="display"></a>Displej

### <a name="selection-margin"></a>Okraj výběru

Pokud je vybráno, zobrazí svislý okraj podél levého okraje editoru textová oblast. Můžete kliknout na tento okraj označit celý řádek textu, nebo klikněte a tažením vyberte po sobě jdoucích řádků textu.

|Okraj výběru|Okraj výběru vypnuto|
| - | - |
|![Snímek obrazovky HTMLpageSelectionMarginOn](../../ide/reference/media/vxselmaron.gif)|![Snímek obrazovky HTMLpageSelectionMarginOff](../../ide/reference/media/vxselmaroff.gif)|

### <a name="indicator-margin"></a>Okraj indikátoru

Pokud je vybráno, zobrazí svislý okraj mimo levého okraje editoru textová oblast. Po kliknutí na toto rozpětí, zobrazí ikonu a popis, který se vztahují na text. Zarážky nebo úloha klávesové zkratky seznamu se zobrazí v okraj indikátoru. Nelze vytisknout informace okraj indikátoru.

### <a name="highlight-current-line"></a>Zvýraznit aktuální řádek

Pokud je vybráno, zobrazí šedé okolo řádek kódu, ve kterém se nachází kurzor.

### <a name="show-structure-guide-lines"></a>Zobrazit vodicí čáry struktury

Pokud je vybráno, svislé čáry zobrazí v editoru tento řádek nahoru strukturovaný kód bloky, které vám umožní snadno identifikovat jednotlivé bloky kódu.

## <a name="see-also"></a>Viz také:

- [Možnosti, Textový editor, Všechny jazyky](../../ide/reference/options-text-editor-all-languages.md)
- [Možnosti, Textový editor, Všechny jazyky, Tabulátory](../../ide/reference/options-text-editor-all-languages-tabs.md)
- [Možnosti, Textový editor, Přípona souboru](../../ide/reference/options-text-editor-file-extension.md)
- [Identifikování a přizpůsobení klávesových zkratek](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)
- [Vlastní nastavení editoru](../../ide/customizing-the-editor.md)
- [Používání atributu IntelliSense](../../ide/using-intellisense.md)