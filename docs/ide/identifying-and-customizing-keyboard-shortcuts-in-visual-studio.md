---
title: Identifikovat a přizpůsobení klávesových zkratek v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.Keyboard
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5ed1806ce5810814c8ea2ce9c08462ecc8f9fd77
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747226"
---
# <a name="identify-and-customize-keyboard-shortcuts-in-visual-studio"></a>Identifikovat a přizpůsobení klávesových zkratek v sadě Visual Studio

Můžete určit klávesové zkratky pro příkazy sady Visual Studio, tyto zkratky přizpůsobit a exportovat je, aby je mohli používat ostatní uživatelé. Mnoho zkratek vždy vyvolá stejné příkazy, ale chování zkratky se může lišit v závislosti na následujících podmínkách:

- Výchozí nastavení prostředí, které jste vybrali při prvním spuštění sady Visual Studio (například obecný vývoj nebo Visual C#).

- Zda jste přizpůsobili chování zkratky.

- Kontext použitý při výběru zástupce. Například **F2** vyvolá zástupce `Edit.EditCell` příkaz, pokud používáte **nastavení návrháře** a `File.Rename` příkaz, pokud používáte **Team Explorer**.

Bez ohledu na nastavení, přizpůsobení a kontext, můžete vždy najít a změnit klávesové zkratky v **možnosti** dialogové okno. Můžete také vyhledat výchozí klávesové zkratky pro několik desítek příkazy v [výchozí klávesové zkratky pro často používané příkazy](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md), a najdete úplný seznam všech výchozí zkratky (na základě **obecné Nastavení pro vývoj**) v [výchozí klávesové zkratky](../ide/default-keyboard-shortcuts-in-visual-studio.md).

Pokud je klávesová zkratka přiřazena k příkazu v globálním kontextu a bez jiných kontextů, tato zkratka vždy vyvolá daný příkaz. Klávesová zkratka může být však přiřazena k jednomu příkazu v globálním kontextu a k jinému příkazu ve specifickém kontextu. Používáte-li takovou klávesovou zkratku v konkrétním kontextu, tato zkratka vyvolá příkaz pro konkrétní kontext, nikoli pro globální kontext.

> [!NOTE]
> Vaše nastavení a edice sady Visual Studio může změnit názvy a umístění příkazů nabídky a možnosti, které se zobrazí v dialogových oknech. Toto téma je založena na **obecné nastavení vývoj**.

## <a name="identify-a-keyboard-shortcut"></a>Identifikovat klávesové zkratky

1. Na řádku nabídek zvolte **nástroje** > **možnosti**.

2. Rozbalte položku **prostředí**a potom zvolte **klávesnice**.

   ![Zobrazit klávesové zkratky v dialogové okno Možnosti](../ide/media/optionskeyboard.png)

3. V **zobrazit příkazy obsahující** zadejte část nebo celý název příkazu bez mezer.

   Například můžete najít příkazy pro `solutionexplorer`.

4. V seznamu zvolte správný příkaz.

    Například můžete `View.SolutionExplorer`.

5. Pokud příkaz obsahuje klávesové zkratky, zobrazí se v **zástupce pro vybraný příkaz** seznamu.

   ![Zobrazení zástupce pro zadaný příkaz](../ide/media/viewshortcut.png)

## <a name="customize-a-keyboard-shortcut"></a>Přizpůsobení klávesové zkratky

1. Na řádku nabídek zvolte **nástroje** > **možnosti**.

2. Rozbalte **prostředí** složku a potom zvolte **klávesnice**.

3. Volitelné: Filtrovat seznam příkazů, tak, že zadáte část nebo celý název příkazu, bez mezer, **zobrazit příkazy obsahující** pole.

4. V seznamu vyberte příkaz, ke kterému chcete přiřadit klávesovou zkratku.

    V **použití nového zástupce v** vyberte oblast funkcí, ve které chcete použít zástupce.

    Například můžete **globální** Pokud chcete zástupce pro práci v všechny kontexty. Můžete použít jakoukoli zkratku, která není namapována (jako globální) v jiném editoru. V opačném případě editor zkratku přepíše.

    > [!NOTE]
    > Následující klíče nelze přiřadit jako součást klávesové zkratky v **globální**: tisk navigátoru obrazovky nebo SysRq posuňte zámku, pozastavit nebo přerušení, karta Caps Lock, vložení, domů, End, Page Up, Page Down, klávesu s logem Windows, klíč aplikace, všechny na šipku klíče, nebo zadejte; NumLock, odstranit, nebo zrušte na numerické klávesnici; kombinace kláves Ctrl + Alt + Delete.

6. V **stiskněte zástupce klíče** zadejte zástupce, který chcete použít.

    > [!NOTE]
    > Můžete vytvořit zástupce, který kombinuje písmeno s **Alt** klíč, **Ctrl** klíč, nebo obojí. Můžete také vytvořit zástupce, který kombinuje **Shift** klíč a písmeno s **Alt** klíč, **Ctrl** klíč, nebo obojí.

     Pokud zástupce je již přiřazen do jiného příkazu, zobrazí se v **zástupce aktuálně používané** pole. V takovém případě zvolte **Backspace** klíč odstranit tento zástupce, než se pokusíte jiný.

    ![Zadejte jiný zástupce pro příkaz](../ide/media/reassignshortcut.png)

7. Vyberte **přiřadit** tlačítko.

    > [!NOTE]
    > Pokud zadáte jiný zástupce pro příkaz, vyberte **přiřadit** tlačítko a potom vyberte **zrušit** tlačítko zavření dialogového okna, ale není vrácení změn.

## <a name="share-custom-keyboard-shortcuts"></a>Sdílet vlastní klávesové zkratky

Vlastní klávesové zkratky je možné sdílet exportováním do souboru a předáním souboru ostatním, aby data mohli importovat.

### <a name="to-export-only-keyboard-shortcuts"></a>Export pouze klávesových zkratek

1. Na řádku nabídek zvolte **nástroje** > **nastavení importu a exportu**.

2. Zvolte **Export vybrané nastavení prostředí**a potom zvolte **Další** tlačítko.

3. V části **nastavení, které chcete exportovat?**, zrušte **všechna nastavení** zaškrtněte políčko, rozbalte položku **možnosti**a potom rozbalte **prostředí**.

4. Vyberte **klávesnice** zaškrtněte políčko a potom vyberte **Další** tlačítko.

    ![Exportovat jenom vlastní klávesové zkratky](../ide/media/exportshortcuts.png)

5. V **co chcete název souboru nastavení?** a **uložit soubor s nastaveními v tomto adresáři** polí buď ponechte výchozí hodnoty nebo zadejte jiné hodnoty a potom vyberte  **Dokončit** tlačítko.

    Ve výchozím nastavení jsou zástupce uloží do souboru v *%USERPROFILE%\Documents\Visual Studio 2017\Settings* složky. Název souboru zobrazuje datum, kdy jste exportovali nastavení a rozšíření *.vssettings*.

### <a name="to-import-only-keyboard-shortcuts"></a>Import pouze klávesových zkratek

1. Na řádku nabídek zvolte **nástroje** > **nastavení importu a exportu**.

2. Vyberte **importovat vybrané nastavení prostředí** možnost tlačítko a potom vyberte **Další** tlačítko.

3. Vyberte **Ne, přímo importovat nové nastavení, přepsal aktuální nastavení** možnost tlačítko a potom vyberte **Další** tlačítko.

4. V části **Moje nastavení**, vyberte soubor, který obsahuje zkratky, které chcete importovat, nebo zvolte **Procházet** tlačítko vyhledat správný soubor.

5. Vyberte **Další** tlačítko.

6.  V části **nastavení, které chcete importovat?**, zrušte **všechna nastavení** zaškrtněte políčko, rozbalte položku **možnosti**a potom rozbalte **prostředí**.

7. Vyberte **klávesnice** zaškrtněte políčko a potom vyberte **Dokončit** tlačítko.

    ![Importovat pouze vlastní klávesové zkratky](../ide/media/importshortcuts.png)

## <a name="see-also"></a>Viz také:

- [Funkce pro usnadnění přístupu sady Visual Studio](../ide/reference/accessibility-features-of-visual-studio.md)