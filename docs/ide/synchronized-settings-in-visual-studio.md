---
title: Synchronizovat nastavení
ms.date: 12/10/2018
ms.topic: conceptual
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b5f3eec072988c7ab093f305cf2903ae1079cc2
ms.sourcegitcommit: 87d7123c09812534b7b08743de4d11d6433eaa13
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57221876"
---
# <a name="synchronize-visual-studio-settings-across-multiple-computers"></a>Synchronizovat nastavení sady Visual Studio mezi několik počítačů

Při přihlášení k sadě Visual Studio na několika počítačích pomocí stejného účtu individuálního nastavení, lze nastavení synchronizovat napříč počítači.

## <a name="synchronized-settings"></a>Synchronizovaná nastavení

Ve výchozím nastavení jsou synchronizována následující nastavení:

- Nastavení pro vývoj. Vyberte sadu nastavení při prvním spuštění sady Visual Studio, ale můžete výběr můžete kdykoli změnit. Další informace najdete v tématu [nastavení prostředí](../ide/environment-settings.md).

- Aliasy příkazu definované uživatelem. Další informace o definici aliasů příkazu naleznete v tématu [aliasy příkazů sady Visual Studio](../ide/reference/visual-studio-command-aliases.md).

- Rozložení oken uživatelem definované v **okno** > **spravovat rozložení oken** stránky.

- Následující možnosti **nástroje** > **možnosti** stránky:

   - Motiv a nabídky panelu nastavení malých a velkých písmen na **prostředí** > **Obecné** stránka možností.

   - Všechna nastavení na **prostředí** > **písma a barvy** stránka možností.

   - Všechny klávesové zkratky na **prostředí** > **klávesnice** stránka možností.

   - Všechna nastavení na **prostředí** > **karty a Windows** stránka možností.

   - Všechna nastavení na **prostředí** > **spuštění** stránka možností.

   - Všechna nastavení na **textový Editor** možnosti stránky.

   - Všechna nastavení na **návrháře XAML** možnosti stránky.

## <a name="turn-off-synchronized-settings-on-a-particular-computer"></a>Vypnout synchronizovaná nastavení v určitém počítači

Synchronizovaná nastavení pro sadu Visual Studio jsou ve výchozím nastavení zapnutá. Synchronizovaná nastavení v počítači můžete vypnout tak, že přejdete **nástroje** > **možnosti** > **prostředí**  >   **Účty** stránky a zrušíte zaškrtnutí **synchronizovat nastavení v zařízení při přihlášení k sadě Visual Studio**.

Například pokud se rozhodnete nesynchronizovat nastavení sady Visual Studio v počítači "A", všechny změny nastavení na počítači "A" nezobrazí počítače "B" nebo "C". Počítače, "B" a "C" bude dál k synchronizaci mezi sebou, ale ne s počítači "A".

> [!NOTE]
> Pokud se rozhodnete nesynchronizovat nastavení podle zrušením výběru možnosti v **nástroje** > **možnosti** > **prostředí**  >  **Účty** neovlivní stránky nebo jiných verzí, edicí sady Visual Studio, které máte na stejném počítači. Tyto-souběžnými instalacemi sady Visual Studio nadále synchronizovat svoje nastavení (Pokud jste příliš zrušte zaškrtnutí možnosti,).

## <a name="synchronize-settings-across-visual-studio-family-products-and-editions"></a>Synchronizace nastavení mezi produkty řady Visual Studio a edice

Nastavení se synchronizují napříč verze a edice sady Visual Studio nainstalované *vedle sebe*. Nastavení jsou také synchronizovat napříč produkty řady Visual Studio, včetně nástroje Blend for Visual Studio. Jednotlivé řady však může mít svůj vlastní nastavení, která se nesdílejí s Visual Studio. Například nastavení specifická pro Blend for Visual Studio na počítači, který "A" nejsou sdíleny s Visual Studio na počítačích "A" nebo "B".

## <a name="side-by-side-synchronized-settings"></a>Synchronizovaná nastavení vedle sebe

::: moniker range="vs-2017"

Určitá nastavení, například rozložení okna nástroje nejsou sdíleny mezi různé-souběžnými instalacemi sady Visual Studio. *CurrentSettings.vssettings* ve *%userprofile%\Documents\Visual Studio 2017\Settings* je do složky specifické pro instalace, který je podobný *%localappdata%\ Microsoft\VisualStudio\15.0_xxxxxxxx\Settings*.

> [!NOTE]
> Pokud chcete použít nové nastavení specifická pro instalace, proveďte novou instalací. Když upgradujete existující instalaci sady Visual Studio, použije se existující sdílené umístění.

Pokud aktuálně máte – souběžnými instalacemi sady Visual Studio a chcete používat nové umístění souboru nastavení specifická pro instalace, postupujte podle těchto kroků:

1. Upgrade na Visual Studio 2017 verze 15.3 nebo novější.

2. Použití **importem nastavení** průvodce a vyexportujte všechna existující nastavení do umístění mimo *%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx* složky.

3. Otevřít **Developer Command Prompt for VS 2017** a spusťte `devenv /resetuserdata`.

1. Spusťte sadu Visual Studio a naimportujte uložená nastavení ze souboru s vyexportovaným nastavením.

::: moniker-end

::: moniker range=">=vs-2019"

Určitá nastavení, například rozložení okna nástroje nejsou sdíleny mezi různé-souběžnými instalacemi sady Visual Studio. *CurrentSettings.vssettings* ve *%userprofile%\Documents\Visual Studio 2019\Settings* je do složky specifické pro instalace, který je podobný *%localappdata%\ Microsoft\VisualStudio\16.0_xxxxxxxx\Settings*.

::: moniker-end

## <a name="see-also"></a>Viz také:

- [Přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)
- [Nastavení prostředí](../ide/environment-settings.md)
- [Prostředí > dialogové okno Možnosti účty](reference/accounts-environment-options-dialog-box.md)
