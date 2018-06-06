---
title: Synchronizovat nastavení
ms.date: 01/23/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.RoamingSettings
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 633767e66a4b3d976999574c885a3e6f7a06ddcf
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766126"
---
# <a name="synchronize-visual-studio-settings-across-multiple-computers"></a>Synchronizovat nastavení sady Visual Studio mezi více počítači

Při přihlášení k sadě Visual Studio na několika počítačích pomocí stejného účtu, přizpůsobení, dají se nastavení synchronizovat mezi počítače.

## <a name="synchronized-settings"></a>Synchronizovaná nastavení

Ve výchozím nastavení jsou synchronizovány následující nastavení:

- Nastavení pro vývoj. Musíte vybrat sadu nastavení při prvním spuštění sady Visual Studio, ale můžete změnit výběr kdykoli. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

- Aliasy příkazů definovaný uživatelem. Další informace o tom, jak definovat aliasy příkazů najdete v tématu [aliasy příkazů sady Visual Studio](../ide/reference/visual-studio-command-aliases.md).

- Rozložení oken uživatelem definované v **okno** > **spravovat rozložení oken** stránky.

- Následující možnosti v **nástroje** > **možnosti** stránky:

   - Motiv a nabídky panelu nastavení velká a malá písmena na **prostředí** > **Obecné** stránka Možnosti.

   - Všechna nastavení na **prostředí** > **písma a barev** stránka Možnosti.

   - Všechny klávesové zkratky, na **prostředí** > **klávesnice** stránka Možnosti.

   - Všechna nastavení na **prostředí** > **karty a okna** stránka Možnosti.

   - Všechna nastavení na **prostředí** > **spuštění** stránka Možnosti.

   - Všechna nastavení na **textového editoru** možnosti stránky.

   - Všechna nastavení na **návrháře XAML** možnosti stránky.

## <a name="turn-off-synchronized-settings-on-a-particular-computer"></a>Vypnout synchronizovaná nastavení v určitém počítači

Synchronizovaná nastavení pro sadu Visual Studio jsou ve výchozím nastavení zapnuté. Synchronizovaná nastavení v počítači můžete vypnout přechodem na **nástroje** > **možnosti** > **prostředí**  >   **Účty** stránku a zrušte zaškrtnutí **synchronizaci nastavení mezi zařízeními při přihlášení k sadě Visual Studio**. Například pokud se rozhodnete nechcete synchronizovat nastavení sady Visual Studio v počítači "A", všechny změny nastavení na počítač "A" se nezobrazí na počítač "B", nebo počítač "C". Počítače, "B" a "C" budou dál k synchronizaci mezi sebou, ale ne při počítač "A".

## <a name="reset-settings"></a>Resetovat nastavení

Pomocí následujícího postupu můžete obnovit všechna nastavení kolekce výchozí nastavení:

1. V sadě Visual Studio, vyberte **nástroje** > **nastavení importu a exportu** otevřete **Průvodce importem a exportem nastavení**.

1. V **Průvodce importem a exportem nastavení**, vyberte **obnovit nastavení** a pak vyberte **Další**.

   ![Průvodce importem a exportem nastavení v sadě Visual Studio](media/reset-all-settings.png)

1. Na **uložit aktuální nastavení** vyberte buď **Ano** nebo **ne** a pak vyberte **Další**.

1. Na **zvolte výchozí kolekci nastavení** , zvolte kolekci a pak vyberte **Dokončit**.

   ![Kolekce nastavení v sadě Visual Studio](media/settings-collections.png)

1. Na **kompletní obnovení** vyberte **Zavřít**.

## <a name="synchronize-settings-across-visual-studio-family-products-and-editions"></a>Synchronizovat nastavení v sadě Visual Studio rodiny produktů a verzí

Nastavení lze synchronizovat mezi libovolná edice sady Visual Studio, včetně edice Community. Nastavení jsou také synchronizovány mezi produkty řady Visual Studio. Ale těchto rodiny produktů může mít svůj vlastní nastavení, které nejsou sdílet pomocí sady Visual Studio. Například nastavení specifické pro jeden produkt na počítači, který "A" jsou sdíleny s jiného produktu v počítači "B", ale ne pomocí sady Visual Studio na počítačích "A" nebo "B".

## <a name="side-by-side-synchronized-settings"></a>Synchronizovaná nastavení vedle sebe

Ve verzi Visual Studio 2017 15.3 a novější nejsou mezi různé vedle sebe instalace Visual Studio 2017 sdílená určitá nastavení jako nástroj rozložení okna. *CurrentSettings.vssettings* souboru v *%userprofile%\Documents\Visual Studio 2017\Settings* v složka specifická pro instalace, který je podobný *%localappdata%\ Microsoft\VisualStudio\15.0_xxxxxxxx\Settings*.

> [!NOTE]
> Chcete-li použít nové nastavení specifických pro instalaci, proveďte novou instalací. Když provádíte upgrade existující instalace Visual Studio 2017 na nejnovější aktualizaci, používá existující sdílené umístění.

Pokud aktuálně máte vedle sebe instalace Visual Studio 2017 a chcete používat nové umístění souboru nastavení specifických pro instalaci, postupujte takto:

1. Upgrade na Visual Studio 2017 verze 15.3 nebo novější.

1. Použití **Import\Export nastavení** průvodce můžete exportovat všechna existující nastavení některé umístění mimo *%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx* složky.

1. Otevřete **příkazový řádek vývojáře pro VS 2017** upgradovaný instalaci sady Visual Studio a spustit `devenv /resetuserdata`.

1. Spusťte sadu Visual Studio a naimportujte uložená nastavení ze souboru s vyexportovaným nastavením.

## <a name="see-also"></a>Viz také:

[Přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)
