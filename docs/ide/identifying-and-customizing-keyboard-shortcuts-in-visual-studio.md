---
title: "Identifikování a přizpůsobení klávesových zkratek v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.Environment.Keyboard
helpviewer_keywords:
- keyboard shortcuts [Visual Studio], customizing
- importing shortcut keys [Visual Studio]
- shortcut key combinations [Visual Studio]
- commands [Visual Studio], shortcut keys
- custom shortcut keys [Visual Studio]
- customizing keyboard shortcuts [Visual Studio]
- exporting shortcut keys [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7258a1ba99764fa7af7ce73874f447db99b8b168
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="identifying-and-customizing-keyboard-shortcuts-in-visual-studio"></a>Identifikování a přizpůsobení klávesových zkratek v sadě Visual Studio

Můžete určit klávesové zkratky pro příkazy sady Visual Studio, tyto zkratky přizpůsobit a exportovat je, aby je mohli používat ostatní uživatelé. Mnoho zkratek vždy vyvolá stejné příkazy, ale chování zkratky se může lišit v závislosti na následujících podmínkách:

- Výchozí nastavení prostředí, které jste vybrali při prvním spuštění sady Visual Studio (například obecný vývoj nebo Visual C#).

- Zda jste přizpůsobili chování zkratky.

- Kontext použitý při výběru zástupce. Například zkratka F2 vyvolá příkaz Edit.EditCell, pokud používáte Návrháře nastavení, a příkaz File.Rename, pokud používáte Průzkumník týmových projektů.

Bez ohledu na nastavení, přizpůsobení a kontext, můžete vždy najít a změnit klávesové zkratky v **možnosti** dialogové okno. Můžete také vyhledat výchozí klávesové zkratky pro několik desítek příkazy v [výchozí klávesové zkratky pro často použít příkazy](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md), a najdete úplný seznam všech výchozí zkratky (na základě obecné vývoj Nastavení) v [výchozí klávesové zkratky](../ide/default-keyboard-shortcuts-in-visual-studio.md).

Pokud je klávesová zkratka přiřazena k příkazu v globálním kontextu a bez jiných kontextů, tato zkratka vždy vyvolá daný příkaz. Klávesová zkratka může být však přiřazena k jednomu příkazu v globálním kontextu a k jinému příkazu ve specifickém kontextu. Používáte-li takovou klávesovou zkratku v konkrétním kontextu, tato zkratka vyvolá příkaz pro konkrétní kontext, nikoli pro globální kontext.

> [!NOTE]
> Vaše nastavení a edice sady Visual Studio může změnit názvy a umístění příkazů nabídky a možnosti, které se zobrazí v dialogových oknech. Toto téma je založena na **obecné nastavení vývoj**.

## <a name="identifying-a-keyboard-shortcut"></a>Určení klávesové zkratky

1. Na řádku nabídek zvolte **nástroje**, **možnosti**.

2. Rozbalte položku **prostředí**a potom zvolte **klávesnice**.

   ![Zobrazit klávesové zkratky v dialogovém okně Možnosti](../ide/media/optionskeyboard.png "OptionsKeyboard")

3. V **zobrazit příkazy obsahující** zadejte část nebo celý název příkazu bez mezer.

   Například můžete najít příkazy pro `solutionexplorer`.

4. V seznamu zvolte správný příkaz.

    Například můžete **View.SolutionExplorer**.

5. Pokud příkaz obsahuje klávesové zkratky, zobrazí se v **zástupce pro vybraný příkaz** seznamu.

   ![Zobrazení zástupce pro zadaný příkaz](../ide/media/viewshortcut.png "ViewShortcut")

## <a name="customizing-a-keyboard-shortcut"></a>Přizpůsobení klávesové zkratky

1. Na řádku nabídek zvolte **nástroje**, **možnosti**.

2. Rozbalte **prostředí** složku a potom zvolte **klávesnice**.

3. Volitelné: Filtrovat seznam příkazů, tak, že zadáte část nebo celý název příkazu, bez mezer, **zobrazit příkazy obsahující** pole.

4. V seznamu vyberte příkaz, ke kterému chcete přiřadit klávesovou zkratku.

V **použití nového zástupce v** vyberte oblast funkcí, ve které chcete použít zástupce.

    For example, you can choose **Global** if you want the shortcut to work in all contexts. You can use any shortcut that isn't mapped (as Global) in another editor. Otherwise, the editor overrides the shortcut.

    > [!NOTE]
    > You can't assign the following keys as part of a keyboard shortcut in **Global**: Print Scrn/Sys Rq, Scroll Lock, Pause/Break, Tab, Caps Lock, Insert, Home, End, Page Up, Page Down, the Windows logo key, the Application key, any of the Arrow keys, or Enter; Num Lock, Delete, or Clear on the numeric keypad; the Ctrl+Alt+Delete key combination.

6. V **stiskněte zástupce klíče** zadejte zástupce, který chcete použít.

    > [!NOTE]
    > Můžete vytvořit zástupce, který kombinuje písmeno s klávesou Alt, klávesou Ctrl nebo oběma klávesami. Můžete také vytvořit zástupce, který kombinuje klávesu Shift a písmeno s klávesou Alt, klávesou Ctrl nebo oběma klávesami.

     Pokud zástupce je již přiřazen do jiného příkazu, zobrazí se v **zástupce aktuálně používané** pole. V takovém případě stisknutím klávesy Backspace tuto klávesovou zkratku smažte a zkuste jinou.

    ![Zadejte jiný zástupce pro příkaz](../ide/media/reassignshortcut.png "ReassignShortcut")

7. Vyberte **přiřadit** tlačítko.

    > [!NOTE]
    > Pokud zadáte jiný zástupce pro příkaz, vyberte **přiřadit** tlačítko a potom vyberte **zrušit** tlačítko zavření dialogového okna, ale není vrácení změn.

## <a name="sharing-custom-keyboard-shortcuts"></a>Sdílení vlastní klávesové zkratky

Vlastní klávesové zkratky je možné sdílet exportováním do souboru a předáním souboru ostatním, aby data mohli importovat.

### <a name="to-export-only-keyboard-shortcuts"></a>Export pouze klávesových zkratek

1. Na řádku nabídek zvolte **nástroje**, **nastavení importu a exportu**.

2. Zvolte **Export vybrané nastavení prostředí**a potom zvolte **Další** tlačítko.

3. V části **nastavení, které chcete exportovat?**, zrušte **všechna nastavení** zaškrtněte políčko, rozbalte položku **možnosti**a potom rozbalte **prostředí**.

4. Vyberte **klávesnice** zaškrtněte políčko a potom vyberte **Další** tlačítko.

    ![Export pouze přizpůsobené klávesové zkratky](../ide/media/exportshortcuts.png "ExportShortcuts")

5. V **co chcete název souboru nastavení?** a **uložit soubor s nastaveními v tomto adresáři** polí buď ponechte výchozí hodnoty nebo zadejte jiné hodnoty a potom vyberte  **Dokončit** tlačítko.

    Ve výchozím nastavení jsou v souboru ve složce %USERPROFILE%\Documents\Visual Studio 2017\Settings uloží zástupce. Název souboru zobrazuje datum, kdy jste nastavení exportovali, a přípona je .vssettings.

### <a name="to-import-only-keyboard-shortcuts"></a>Import pouze klávesových zkratek

1. Na řádku nabídek zvolte **nástroje**, **nastavení importu a exportu**.

2. Vyberte **importovat vybrané nastavení prostředí** možnost tlačítko a potom vyberte **Další** tlačítko.

3. Vyberte **Ne, přímo importovat nové nastavení, přepsal aktuální nastavení** možnost tlačítko a potom vyberte **Další** tlačítko.

4. V části **Moje nastavení**, vyberte soubor, který obsahuje zkratky, které chcete importovat, nebo zvolte **Procházet** tlačítko vyhledat správný soubor.

5. Vyberte **Další** tlačítko.

6.  V části **nastavení, které chcete importovat?**, zrušte **všechna nastavení** zaškrtněte políčko, rozbalte položku **možnosti**a potom rozbalte **prostředí**.

7. Vyberte **klávesnice** zaškrtněte políčko a potom vyberte **Dokončit** tlačítko.

    ![Importovat pouze přizpůsobené klávesové zkratky](../ide/media/importshortcuts.png "ImportShortcuts")

## <a name="see-also"></a>Viz také

[Funkce sady Visual Studio pro usnadnění přístupu](../ide/reference/accessibility-features-of-visual-studio.md)