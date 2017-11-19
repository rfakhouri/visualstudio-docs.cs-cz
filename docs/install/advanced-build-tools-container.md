---
title: "Rozšířené příklad pro kontejnery | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e03835db-a616-41e6-b339-92b41d0cfc70
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: c1eb932eb079bca61eb5cea0959c56f00379114c
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="advanced-example-for-containers"></a>Pokročilé příklad kontejnery

Ukázkový soubor Docker v [nainstalovat nástroje sestavení do kontejneru](build-tools-container.md) vždy používá nejnovější microsoft/windowsservercore bitové kopie a nejnovější verzi instalačního programu Visual Studio sestavení 2017 nástroje. Pokud publikujete, aby k této bitové kopie [Docker registru](https://azure.microsoft.com/services/container-registry) ostatním uživatelům pro vyžádání obsahu, může být tuto bitovou kopii pro mnoho scénářů v pořádku. V praxi, ale je dnes běžné specifické o jaké základní bitovou kopii, můžete použít, jaké binární soubory můžete stáhnout, a který nástroj verze instalaci.

Následující příklad soubor Docker používá značku určité verze microsoft/windowsservercore bitové kopie. Pomocí s konkrétní značkou tag pro základní bitovou kopii je maloobchodech a usnadňuje mějte na paměti, že vytváření nebo opětovné vytvoření bitové kopie vždycky má stejné základ.

> [!NOTE]
> Visual Studio nelze nainstalovat do microsoft/windowsservercore:10.0.14393.1593, který obsahuje známé problémy, které spouští instalační program v kontejneru. Další informace najdete v tématu [známé problémy](build-tools-container-issues.md).

Tento příklad používá také 2017 nástroje pro sestavení zaváděcí nástroj, který instaluje konkrétní verzi vytvořené ve stejnou dobu jako zavaděč. Produkt může stále aktualizovat prostřednictvím kanálu verze, ale není praktické scénář pro kontejnery, které by obvykle znovu sestavit. Pokud chcete získat adresy URL pro určitou kanál, můžete stáhnout z https://aka.ms/vs/15/release/channel kanál, otevřete soubor JSON a zkontrolujte adresy URL zaváděcího nástroje. Další informace najdete v tématu [vytvořit síťovou instalaci sady Visual Studio](create-a-network-installation-of-visual-studio.md).

```dockerfile
# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:d841bd78721c74f9b88e2700f5f3c2d66b54cb855b8acb4ab2c627a76a46301d
FROM microsoft/windowsservercore:10.0.14393.1770

# Use PowerShell commands to download, validate hashes, etc.
SHELL ["powershell.exe", "-ExecutionPolicy", "Bypass", "-Command", "$ErrorActionPreference='Stop'; $ProgressPreference='SilentlyContinue'; $VerbosePreference = 'Continue';"]

# Download Build Tools 15.4.27004.2005 and other useful tools.
ENV VS_BUILDTOOLS_URI=https://aka.ms/vs/15/release/6e8971476/vs_buildtools.exe \
    VS_BUILDTOOLS_SHA256=D482171C7F2872B6B9D29B116257C6102DBE6ABA481FAE4983659E7BF67C0F88 \
    NUGET_URI=https://dist.nuget.org/win-x86-commandline/v4.1.0/nuget.exe \
    NUGET_SHA256=4C1DE9B026E0C4AB087302FF75240885742C0FAA62BD2554F913BBE1F6CB63A0

# Download tools to C:\Bin and install Build Tools excluding workloads and components with known issues.
RUN New-Item -Path C:\Bin, C:\TEMP -Type Directory | Out-Null; \
    [System.Environment]::SetEnvironmentVariable('PATH', "\"${env:PATH};C:\Bin\"", 'Machine'); \
    function Fetch ([string] $Uri, [string] $Path, [string] $Hash) { \
      Invoke-RestMethod -Uri $Uri -OutFile $Path; \
      if ($Hash -and ((Get-FileHash -Path $Path -Algorithm SHA256).Hash -ne $Hash)) { \
        throw "\"Download hash for '$Path' incorrect\""; \
      } \
    }; \
    Fetch -Uri $env:NUGET_URI -Path C:\Bin\nuget.exe -Hash $env:NUGET_SHA256; \
    Fetch -Uri $env:VS_BUILDTOOLS_URI -Path C:\TEMP\vs_buildtools.exe -Hash $env:VS_BUILDTOOLS_SHA256; \
    Fetch -Uri 'https://aka.ms/vscollect.exe' -Path C:\TEMP\collect.exe; \
    $p = Start-Process -Wait -PassThru -FilePath C:\TEMP\vs_buildtools.exe -ArgumentList '--quiet --wait --norestart --nocache --installPath C:\BuildTools --all --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 --remove Microsoft.VisualStudio.Component.Windows81SDK'; \
    if (($ret = $p.ExitCode) -and ($ret -ne 3010)) { C:\TEMP\collect.exe; throw ('Install failed with exit code 0x{0:x}' -f $ret) }

# Restore default shell for Windows containers.
SHELL ["cmd.exe", "/s", "/c"]

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

Tento příklad stáhne konkrétních nástrojů a ověří, že se hodnoty hash shodují. Také stažení nejnovější sady Visual Studio a nástroj kolekce protokolu .NET tak, že pokud dojde k selhání instalace, můžete zkopírovat protokoly na hostitelském počítači k analýze selhání.

```shell
> docker build -t buildtools:15.4.27004.2005 -t buildtools:latest -m 2GB .
Sending build context to Docker daemon
...
Step 4/7 : RUN New-Item -Path C:\Bin, C:\TEMP -Type Directory | Out-Null; ...
 ---> Running in 4b62b4ce3a3c
Install failed with exit code 0x643
At line:1 char:1
+ throw ('Install failed with exit code 0x{0:x}' -f 1603)
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (Install failed with exit code 0x643:String) [], RuntimeException
    + FullyQualifiedErrorId : Install failed with exit code 0x643

> docker cp 4b62b4ce3a3c:C:\Users\ContainerAdministrator\AppData\Local\TEMP\vslogs.zip "%TEMP%\vslogs.zip"
```

Po dokončení provádění poslední řádek otevřete "% TEMP%\vslogs.zip" na počítači nebo ohlásit problém na [komunity vývojářů](https://developercommunity.visualstudio.com) webu.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku Tipy pro odstraňování potíží. Taky můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj v prostředí Visual Studio IDE nebo ke sdílení návrh s nám na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi. Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio) (vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také
* [Instalace nástroje sestavení do kontejneru](build-tools-container.md)
* [Známé problémy pro kontejnery](build-tools-container-issues.md)
