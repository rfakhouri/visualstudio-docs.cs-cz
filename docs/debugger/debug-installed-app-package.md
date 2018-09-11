---
title: Ladění balíčku nainstalované aplikace (UPW) | Dokumentace Microsoftu
ms.custom: H1Hack27Feb2017
ms.date: 07/17/2017
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 291f24c6ffdf885cf3d24c5ff163c2f4f911d7ce
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279552"
---
# <a name="debug-an-installed-app-package-in-visual-studio-uwp"></a>Ladění balíčku nainstalované aplikace v aplikaci Visual Studio (UPW)

Kliknutím můžete ladit všechny balíčky nainstalované aplikace **ladit > jiné cíle ladění > Ladit nainstalovaný balíček aplikace**. Tato metoda ladění je k dispozici pro univerzální aplikace Windows (UPW) na těchto zařízeních:

* Windows 10 (není podporováno na telefonech)
* XBox
* HoloLens
* IoT

Další informace o těchto funkcích najdete v blogovém příspěvku o aktualizacích pro [ladění nainstalované balíčky aplikací](https://blogs.msdn.microsoft.com/devops/2016/03/30/updates-for-debugging-installed-app-packages-in-visual-studio-2015-update-2/) a v příspěvku na [vytváření univerzálních aplikací pro Windows (UPW)](https://blogs.msdn.microsoft.com/visualstudio/2016/08/02/universal-windows-apps-targeting-windows-10-anniversary-sdk/).

## <a name="debug-an-installed-app-package-or-running-app-on-a-local-machine-or-device"></a>Ladění nainstalovaného balíčku aplikace nebo aplikace spuštěné na místním počítači nebo zařízení

1. Pomocí projektu UPW otevřít v sadě Visual Studio, klikněte na tlačítko **ladit > jiné cíle ladění > Ladit nainstalovaný balíček aplikace**.

2. Vyberte buď **místního počítače** nebo **zařízení**.

     Pokud se rozhodnete **zařízení**, počítač musí být fyzicky připojen k zařízení s Windows 10.

     ![DebugInstalledAppPackage](../debugger/media/debug-installed-app-pkg.png "DebugInstalledAppPackage")

     Aktuálně spuštěné nainstalované aplikace balíčků se zobrazí v části **systémem** uzlu. Nainstalované balíčky aplikací, které neběží zobrazit až za **neběží**.

3. Vyberte název aplikace, kterou chcete ladit v rámci **systémem** nebo **neběží** a zvolte **Start** nebo, pokud je aplikace spuštěna, zvolte **připojit**.

     Pokud vyberete **nespouštět, ale ladit můj kód při spuštění**, to způsobí, že ladicí program sady Visual Studio k připojení k vaší aplikace při spuštění po jednom vlastní. Toto je účinný způsob, jak ladit ovládací prvek cesty z [různých spuštění metody](/windows/uwp/xbox-apps/automate-launching-uwp-apps), jako je protokol aktivace pomocí vlastních parametrů.

> [!NOTE]
> Visual Studio můžete také připojit k libovolnému spuštěného procesu aplikace UPW tak, že vyberete **ladění**a potom **připojit k procesu**. Připojení ke spuštěnému procesu nevyžaduje původní projekt sady Visual Studio, ale načítají se symboly procesu pomůžou výrazně při ladění procesu, který není nutné původní kód.
  
## <a name="remote"></a> Ladění aplikace nainstalována nebo spuštěna ve vzdáleném počítači 

Při ladění balíčku nainstalované aplikace na vzdáleném počítači poprvé, Visual Studio nainstaluje správná verze nástrojů remote Tools for cílové zařízení. Počítače s Windows 10, XBox, HoloLens a IoT zařízení, musí být cílové zařízení.

1. Na zařízení s Windows 10, povolte [vývojářský režim](/windows/uwp/get-started/enable-your-device-for-development).

2. Pokud se chcete připojit k vzdálenému počítači spuštěná verze pre Tvůrce aktualizace Windows 10, nejprve ručně [nainstalovat a spustit vzdálený ladicí program](../debugger/remote-debugging.md).

     Pro XBox, HoloLens a IoT zařízení a zařízení Windows s Windows 10 Creators Update není nutné ručně nainstalujte vzdálený ladicí program. Nástroje remote tools se automaticky nainstaluje při nasazování aplikace.

3. Klikněte na tlačítko **ladit > jiné cíle ladění > Ladit nainstalovaný balíček aplikace**.

4. V prvním rozevíracím seznamu zvolte **vzdálený počítač**.

5. Zadejte název nebo IP adresu, kterou chcete připojit k počítači.

     ![ChooseRemoteComputer](../debugger/media/debug-remote-app-pkg.png "ChooseRemoteComputer")

     Pokud se nemůžete připojit pomocí názvu počítače (po zvolení **Start**), místo toho použijte IP adresu. Použijte IP adresu pro XBox, HoloLens a IoT zařízení.

5. Zvolte, jak ověřit tak, že vyberete možnost v **režim ověřování**.

    Pro většinu aplikací, ponechte výchozí hodnotu, **univerzální (nešifrovaný protokol)**.

6. Vyberte název aplikace, kterou chcete ladit v rámci **systémem** nebo **neběží** a zvolte **Start** nebo (pro spouštění aplikací) **připojit**.

     Pokud vyberete **nespouštět, ale ladit můj kód při spuštění**, to způsobí, že ladicí program sady Visual Studio k připojení k balíčku aplikace při spuštění po jednom vlastní. Toto je účinný způsob, jak ladit ovládací prvek cesty z [různých spuštění metody](/windows/uwp/xbox-apps/automate-launching-uwp-apps), jako je protokol aktivace pomocí vlastních parametrů.

     Při ladění balíčku nainstalované aplikace na připojeném XBox, HoloLens a IoT zařízení poprvé, Visual Studio nainstaluje správnou verzi vzdáleného ladicího programu pro cílové zařízení. Tato operace může trvat něco času a zobrazí se zpráva ``Starting remote debugger`` když tohle se děje.

     > [!NOTE]
> V přítomné, XBox nebo zařízení HoloLens se aplikace restartuje s ladicím programem připojen, pokud je již spuštěna.

Informace o rozšířené možnosti pro vzdálené nasazení aplikací pro UWP najdete v článku [UPW apps]((/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options) pro nasazení a ladění. 
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)  
 [Vzdálené ladění](../debugger/remote-debugging.md)  
 [Konfigurace brány firewall ve Windows pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md)  
 [Přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md)  
 [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)