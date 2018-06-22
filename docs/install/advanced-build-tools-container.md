---
title: Pokročilé příklad kontejnery
description: ''
ms.custom: ''
ms.date: 04/18/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: e03835db-a616-41e6-b339-92b41d0cfc70
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f708ca73efa4f166f701b4d488ccc609f86e7a4
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283403"
---
# <a name="advanced-example-for-containers"></a>Pokročilé příklad kontejnery

Ukázkový soubor Docker v [nainstalovat nástroje sestavení do kontejneru](build-tools-container.md) vždy používá [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) bitové kopie založené na bitovou kopii nejnovější microsoft/windowsservercore a nejnovější Visual Instalační program Studio 2017 nástroje pro sestavení. Pokud publikujete, aby k této bitové kopie [Docker registru](https://azure.microsoft.com/services/container-registry) ostatním uživatelům pro vyžádání obsahu, může být tuto bitovou kopii pro mnoho scénářů v pořádku. V praxi je však častější specifické o jaké základní bitovou kopii, můžete použít, jaké binární soubory můžete stáhnout, a který nástroj verze instalaci.

Následující příklad soubor Docker používá značku konkrétní verzi rozhraní microsoft/dotnet-framework bitové kopie. Pomocí s konkrétní značkou tag pro základní bitovou kopii je maloobchodech a usnadňuje mějte na paměti, že vytváření nebo opětovné vytvoření bitové kopie vždycky má stejné základ.

> [!NOTE]
> Visual Studio nelze nainstalovat do microsoft/windowsservercore:10.0.14393.1593 nebo žádný obrázek podle toho, který obsahuje známé problémy, které spouští instalační program v kontejneru. Další informace najdete v tématu [známé problémy](build-tools-container-issues.md).

Následující příklad stáhne nejnovější verze 2017 nástroje pro sestavení. Pokud chcete použít starší verzi nástroje sestavení do kontejneru můžete nainstalovat později, musíte nejdřív [vytvořit](create-an-offline-installation-of-visual-studio.md) a [udržovat](update-a-network-installation-of-visual-studio.md) rozložení.

## <a name="install-script"></a>Instalace skriptu

Chcete-li shromažďovat protokoly, když dojde k chybě instalace, v pracovním adresáři vytvořte dávkový skript s názvem "Soubor Install.cmd" s následujícím obsahem:

```shell
@if not defined _echo echo off
setlocal enabledelayedexpansion

call %*
if "%ERRORLEVEL%"=="3010" (
    exit /b 0
) else (
    if not "%ERRORLEVEL%"=="0" (
        set ERR=%ERRORLEVEL%
        call C:\TEMP\collect.exe -zip:C:\vslogs.zip

        exit /b !ERR!
    )
)
```

## <a name="dockerfile"></a>Soubor Docker

V pracovním adresáři vytvořte soubor "Docker" s následujícím obsahem:

```dockerfile
# escape=`

# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:1a66e2b5f3a5b8b98ac703a8bfd4902ae60d307ed9842978df40dbc04ac86b1b
ARG FROM_IMAGE=microsoft/dotnet-framework:4.7.1-20180410-windowsservercore-1709
FROM ${FROM_IMAGE}

# Copy our Install script.
COPY Install.cmd C:\TEMP\

# Download collect.exe in case of an install failure.
ADD https://aka.ms/vscollect.exe C:\TEMP\collect.exe

# Use the latest release channel. For more control, specify the location of an internal layout.
ARG CHANNEL_URL=https://aka.ms/vs/15/release/channel
ADD ${CHANNEL_URL} C:\TEMP\VisualStudio.chman

# Download and install Build Tools excluding workloads and components with known issues.
ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe
RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
    --installPath C:\BuildTools `
    --channelUri C:\TEMP\VisualStudio.chman `
    --installChannelUri C:\TEMP\VisualStudio.chman `
    --all `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
    --remove Microsoft.VisualStudio.Component.Windows81SDK

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

Spusťte následující příkaz k vytvoření bitové kopie v aktuálním pracovním adresáři:

```shell
docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
```

Volitelně můžete předat obojím `FROM_IMAGE` nebo `CHANNEL_URL` argumenty pomocí `--build-arg` přepínač příkazového řádku a zadejte jinou základní bitovou kopii nebo umístění interní rozložení udržovat pevné bitové kopie.

## <a name="diagnosing-install-failures"></a>Diagnostikování selhání instalace

Tento příklad stáhne konkrétních nástrojů a ověří, že se hodnoty hash shodují. Také stažení nejnovější sady Visual Studio a nástroj kolekce protokolu .NET tak, že pokud dojde k selhání instalace, můžete zkopírovat protokoly na hostitelském počítači k analýze selhání.

```shell
> docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
Sending build context to Docker daemon
...
Step 8/10 : RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache ...
 ---> Running in 4b62b4ce3a3c
The command 'cmd /S /C C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe ...' returned a non-zero code: 1603

> docker cp 4b62b4ce3a3c:C:\vslogs.zip "%TEMP%\vslogs.zip"
```

Po dokončení provádění poslední řádek otevřete "% TEMP%\vslogs.zip" na počítači, nebo ohlásit problém na [komunity vývojářů](https://developercommunity.visualstudio.com) webu.

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nepovede instalaci Visual Studio, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://visualstudio.microsoft.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také:

* [Instalace Build Tools do kontejneru](build-tools-container.md)
* [Známé problémy s kontejnery](build-tools-container-issues.md)
* [ID úlohy a součást Visual Studio 2017 nástroje pro sestavení](workload-component-id-vs-build-tools.md)
