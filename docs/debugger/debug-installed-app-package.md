---
title: Ladění balíček nainstalovanou aplikaci (UWP) | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 07/17/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.remote.connection
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- app package, debug
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 9c1406637b6d1dce312b0574cfba3c9a4f7356e8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="debug-an-installed-app-package-in-visual-studio-uwp"></a>Ladění balíček nainstalovanou aplikaci v aplikaci Visual Studio (UWP)

Balíček všechny nainstalované aplikace můžete ladit kliknutím **ladění > jiné cíle ladění > ladění nainstalován balíček aplikace**. Tato metoda ladění je dostupná pro univerzální aplikace Windows (UWP) na těchto zařízeních:

* Windows 10 (na telefonech není podporována)
* XBox
* HoloLens
* IoT

Další informace o těchto funkcích najdete v příspěvku blogu na aktualizace pro [ladění nainstalované balíčky aplikací](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/30/updates-for-debugging-installed-app-packages-in-visual-studio-2015-update-2/) a v příspěvku na [vytváření univerzální aplikace pro Windows (UWP)](https://blogs.msdn.microsoft.com/visualstudio/2016/08/02/universal-windows-apps-targeting-windows-10-anniversary-sdk/).

## <a name="debug-an-installed-app-package-or-running-app-on-a-local-machine-or-device"></a>Ladění nainstalovaným balíčkem aplikace nebo aplikace spuštěna na místním počítači nebo zařízení

1. S UWP projektem otevřeným v sadě Visual Studio, klikněte na tlačítko **ladění > jiné cíle ladění > ladění nainstalován balíček aplikace**.

2. Vyberte buď **místního počítače** nebo **zařízení**.

     Pokud se rozhodnete **zařízení**, počítač musí být fyzicky připojen k zařízením s Windows 10.

     ![DebugInstalledAppPackage](../debugger/media/debug-installed-app-pkg.png "DebugInstalledAppPackage")

     Aktuálně spuštěných nainstalované aplikace balíčky se zobrazí v části **systémem** uzlu. Nainstalované balíčky aplikací, které neběží zobrazit si v části **neběží**.

3. Vyberte název aplikace, kterou chcete ladit pod **systémem** nebo **neběží** a zvolte **spustit** nebo, pokud aplikace je již spuštěna, zvolte **připojit**.

     Pokud vyberete **nespouštějí, ale po jeho spuštění ladění vlastního kódu**, to způsobí, že ladicího programu sady Visual Studio pro připojení k aplikaci při spuštění vlastního najednou. Toto je efektivní způsob, jak ladit cesty ovládací prvek z [různých spuštění metody](/windows/uwp/xbox-apps/automate-launching-uwp-apps), jako je například protokol aktivace pomocí vlastních parametrů.

> [!NOTE]
> Visual Studio můžete taky přiložit všech spuštěných procesů aplikace UWP výběrem **ladění**a potom **připojit k procesu**. Připojení k spuštěných procesů nevyžaduje původní projekt Visual Studio, ale načítání procesu symboly pomůže výrazně při procesu, který nemáte původní kód pro ladění.
  
## <a name="remote"></a> Ladění aplikace nainstalován nebo není spuštěn ve vzdáleném počítači 

Když ladíte balíčku aplikace nainstalované ve vzdáleném počítači poprvé, Visual Studio nainstaluje správnou verzi nástrojů pro vzdálenou pro cílové zařízení. Cílové zařízení musí být v počítači Windows 10, XBox, HoloLens a IoT zařízení.

1. Na zařízení s Windows 10, povolte [režim vývojáře](/windows/uwp/get-started/enable-your-device-for-development).

2. Pokud se připojujete k vzdálenému počítači spuštěna verze pre-Creator aktualizace Windows 10, nejprve ručně [instalace a spuštění vzdáleného ladicího programu](../debugger/remote-debugging.md).

     Pro zařízení s XBox, HoloLens a IoT a Windows zařízení se systémem Windows 10 Creator aktualizace nemusíte ručně nainstalovat vzdáleného ladicího programu. Nástroje pro vzdálenou se automaticky nainstaluje při nasazení aplikace.

3. Klikněte na tlačítko **ladění > jiné cíle ladění > ladění aplikace balíček nainstalován,**.

4. V prvním rozevíracím seznamu vyberte **vzdáleného počítače**.

5. Zadejte název nebo IP adresa počítače, ke kterému chcete přiřadit.

     ![ChooseRemoteComputer](../debugger/media/debug-remote-app-pkg.png "ChooseRemoteComputer")

     Pokud se nemůžete připojit pomocí názvu počítače (po volbě **spustit**), místo toho použít IP adresu. Použijte IP adresu pro XBox, HoloLens a IoT zařízení.

5. Volba způsobu ověření výběrem možnosti v **režim ověřování**.

    Pro většinu aplikací, ponechte výchozí hodnotu, **Universal (nešifrovaného protokolu)**.

6. Vyberte název aplikace, kterou chcete ladit pod **systémem** nebo **neběží** a zvolte **spustit** nebo (pro spouštění aplikací) **připojit**.

     Pokud vyberete **nespouštějí, ale po jeho spuštění ladění vlastního kódu**, to způsobí, že ladicího programu sady Visual Studio pro připojení k vaší balíček aplikace při spuštění vlastního najednou. Toto je efektivní způsob, jak ladit cesty ovládací prvek z [různých spuštění metody](/windows/uwp/xbox-apps/automate-launching-uwp-apps), jako je například protokol aktivace pomocí vlastních parametrů.

     Při ladění balíčku aplikace nainstalované na připojeném zařízení XBox, HoloLens a IoT poprvé, Visual Studio nainstaluje správnou verzi vzdáleného ladicího programu pro cílové zařízení. Tato operace může trvat jenom trocha čas a zobrazí se zpráva ``Starting remote debugger`` při k této situaci.

     > [!NOTE]
> Na k dispozici, XBox nebo HoloLens zařízení bude restartováno aplikace s ladicím programem připojen, pokud je již spuštěna.

Informace o rozšířené možnosti pro vzdálené nasazení aplikace UWP v tématu [nasazení a ladění aplikace UWP](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps.md#advanced-remote-deployment-options). 
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)  
 [Vzdálené ladění](../debugger/remote-debugging.md)  
 [Konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md)  
 [Přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md)  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)