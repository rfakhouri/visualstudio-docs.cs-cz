---
title: Příklady parametrů příkazového řádku pro instalaci
description: Přizpůsobení těchto příkladech, chcete-li vytvořit vlastní instalaci sady Visual Studio z příkazového řádku.
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
ms.assetid: 837F31AA-F121-46e9-9996-F8BCE768E579
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 5a87b5d98d9f3b7453cf0337d529b9ef99815d92
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65614503"
---
# <a name="command-line-parameter-examples-for-visual-studio-installation"></a>Příklady parametrů příkazového řádku pro instalaci sady Visual Studio

Pro ilustraci jak [použít parametry příkazového řádku instalace sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md), tady je několik příkladů, které můžete přizpůsobit tak, aby odpovídala vašim potřebám.

V obou příkladech `vs_enterprise.exe`, `vs_professional.exe` a `vs_community.exe` představují příslušné verzi zaváděcí nástroj Visual Studio, což je soubor malé (přibližně 1 MB), který zahájí proces stahování. Pokud používáte jinou verzi, nahraďte název odpovídající zaváděcího nástroje.

> [!NOTE]
> Všechny příkazy vyžadovat zvýšení oprávnění pro správu a řízení uživatelských účtů, výzva se zobrazí, pokud proces není spuštěn řádku se zvýšenými oprávněními.
>
> [!NOTE]
> Můžete použít `^` znak na konci příkazového řádku ke zřetězení více řádků do jediného příkazu. Alternativně můžete umístit společně na jediném řádku tyto řádky. V prostředí PowerShell, je ekvivalentní prvními (`` ` ``) znaků.

Seznam úloh a součástí, které můžete nainstalovat pomocí příkazového řádku, najdete v článku [ID pracovního vytížení a komponenta Visual Studio](workload-and-component-ids.md) stránky.

## <a name="using---installpath"></a>Pomocí--installPath

* Nainstalujte minimální instanci sady Visual Studio, s žádné interaktivní výzvy, ale zobrazuje průběh:

  ```cmd
   vs_enterprise.exe --installPath C:\minVS ^
   --add Microsoft.VisualStudio.Workload.CoreEditor ^
   --passive --norestart
  ```

* Aktualizace instance sady Visual Studio pomocí příkazového řádku se žádné interaktivní výzvy, ale zobrazuje průběh:

   ```cmd
   vs_enterprise.exe --update --quiet --wait
   vs_enterprise.exe update --wait --passive --norestart --installPath "C:\installPathVS"
   ```

  > [!NOTE]
  > Oba příkazy jsou povinné. První příkaz aktualizuje instalační program sady Visual Studio. Druhý příkaz aktualizuje instanci sady Visual Studio. Aby se zabránilo dialogové okno Řízení uživatelských účtů, spusťte příkazový řádek jako správce.

* Klasické pracovní plochy instanci sady Visual Studio tichou instalaci, Francouzská jazyková sada, vrací pouze v případě, že je nainstalován produkt.

  ```cmd
   vs_enterprise.exe --installPath C:\desktopVS ^
   --addProductLang fr-FR ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --includeRecommended --quiet --wait
  ```

## <a name="using---wait"></a>Pomocí parametru--čekání

* Čekání na instalační program sady Visual Studio a dokončete před provedením dalšího příkazu pomocí v dávkové soubory nebo skripty. Pro dávkové soubory `%ERRORLEVEL%` proměnné prostředí bude obsahovat vrácenou hodnotu příkazu, jak je uvedeno v [použít parametry příkazového řádku instalace sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky. Některé nástroje příkazového vyžadují další parametry, které chcete počkat na dokončení a k získání vrácené hodnoty instalačního programu. Následuje příklad další parametry pro příkaz skriptu prostředí PowerShell spuštění procesu:

   ```cmd
   start /wait vs_professional.exe --installPath "C:\VS" --passive --wait > nul
   echo %errorlevel%
   ```
   ```PS
   $exitCode = Start-Process -FilePath vs_enterprise.exe -ArgumentList "--installPath", "C:\VS", "--passive", "--wait" -Wait -PassThru
   ```
   or
   ```PS
    $startInfo = New-Object System.Diagnostics.ProcessStartInfo
    $startInfo.FileName = "vs_enterprise.exe"
    $startInfo.Arguments = "--all --quiet --wait" 
    $process = New-Object System.Diagnostics.Process
    $process.StartInfo = $startInfo
    $process.Start() 
    $process.WaitForExit()
   ```

* První "– Počkejte" se používá tak, že instalační program sady Visual Studio a druhá ' – počkejte "je používán procesem' Start-" Čekání na dokončení. "-PassThru' parametr je používán procesem' Start-" použití instalačního programu ukončovací kód pro jeho návratovou hodnotu.

## <a name="using---layout"></a>Pomocí parametru--rozložení

* Stáhněte si základní editor sady Visual Studio (nejvíce minimální konfigurace sady Visual Studio). Zahrnout pouze anglické jazykové sady:

  ```cmd
   vs_community.exe --layout C:\VS
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.CoreEditor
  ```

* Stáhněte .NET desktop a webové úlohy .NET spolu s všechny doporučené součásti a rozšíření GitHub. Zahrnout pouze anglické jazykové sady:

  ```cmd
   vs_community.exe --layout C:\VS ^
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.NetWeb ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --add Component.GitHub.VisualStudio ^
   --includeRecommended
  ```

## <a name="using---all"></a>Používání – vše

* Interaktivní instalací všechny úlohy a komponenty, které jsou k dispozici v edici Visual Studio Enterprise:

   ```cmd
   vs_enterprise.exe --all
   ```

## <a name="using---includerecommended"></a>Pomocí--includeRecommended

* Druhý, pojmenovanou instanci sady Visual Studio Professional můžete nainstalujte na počítač s Visual Studio Community edition už nainstalovaná s podporou pro vývoj v Node.js:

   ```cmd
   vs_professional.exe --installPath C:\VSforNode ^
   --add Microsoft.VisualStudio.Workload.Node --includeRecommended --nickname VSforNode
  ```

## <a name="using---remove"></a>Pomocí parametru--odebrat

::: moniker range="vs-2017"

* Odebrat součást nástrojů pro profilaci z výchozího nainstalované instance sady Visual Studio:

  ```cmd
   vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
  ```

::: moniker-end

::: moniker range="vs-2019"

* Odebrat součást nástrojů pro profilaci z výchozího nainstalované instance sady Visual Studio:

  ```cmd
   vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
  ```

::: moniker-end

## <a name="using---path"></a>Pomocí parametru--cesty

::: moniker range="vs-2017"

Tyto parametry příkazového řádku jsou **nové ve verzi 15.7**. Další informace o nich najdete v tématu [použít parametry příkazového řádku instalace sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky.

::: moniker-end

* Pomocí instalace, mezipaměť a sdílené cesty:

  `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache" --path shared="C:\VS\shared"`

* Pomocí jenom cesty instalace a mezipaměti:

  `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache"`

* Pomocí instalace a sdílené cesty:

  `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path shared="C:\VS\shared"`

* Použití pouze instalační cesta:

  `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS"`

## <a name="using-export"></a>Použití možnosti exportovat

::: moniker range="vs-2017"

Tento příkaz příkazového řádku je **novinkou 15.9**. Další informace o tom, najdete v článku [použít parametry příkazového řádku instalace sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky.

::: moniker-end

* Pomocí exportu a uložte výběr z instalace:

  ```cmd
  "C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe" export --installPath "C:\VS" --config "C:\.vsconfig"
  ```

* Uložte vlastní výběr úplně od začátku pomocí exportu:

  ```cmd
  "C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe" export --add Microsoft.VisualStudio.Workload.ManagedDesktop --includeRecommended --config "C:\.vsconfig"
  ```

## <a name="using---config"></a>Pomocí--config

::: moniker range="vs-2017"

Tento parametr příkazového řádku **novinkou 15.9**. Další informace o tom, najdete v článku [použít parametry příkazového řádku instalace sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky.

::: moniker-end

* Instalace úloh a součástí z předchozího uloženého instalace konfiguračního souboru pomocí--config:

  ```cmd
  vs_enterprise.exe --config "C:\.vsconfig" --installPath "C:\VS"
  ```

* Přidání úlohy a komponenty do existující instalace pomocí--config:

  ```cmd
  vs_enterprise.exe modify --installPath "C:\VS" --config "C:\.vsconfig"
  ```

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Příručka správce sady Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [Vytvoření offline instalace sady Visual Studio](create-an-offline-installation-of-visual-studio.md)
* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
