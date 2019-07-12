---
title: Nainstalovat Visual Studio Build Tools do kontejneru
titleSuffix: ''
description: Zjistěte, jak nainstalovat Visual Studio Build Tools do kontejneru Windows pro podporu kontinuální integrace a pracovní postupy průběžné doručování (CI/CD).
ms.date: 07/03/2019
ms.custom: seodec18
ms.topic: conceptual
ms.assetid: d5c038e2-e70d-411e-950c-8a54917b578a
author: heaths
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 24e27c8ca2c75e2345bea4f4393fcb00bba1a0d8
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67821713"
---
# <a name="install-build-tools-into-a-container"></a>Instalace Build Tools do kontejneru

Visual Studio Build Tools můžete nainstalovat do kontejneru Windows pro podporu kontinuální integrace a pracovní postupy průběžné doručování (CI/CD). Tento článek vás provede změny konfigurace Dockeru se vyžadují i co [úlohy a komponenty](workload-component-id-vs-build-tools.md) můžete nainstalovat v kontejneru.

[Kontejnery](https://www.docker.com/what-container) jsou skvělý způsob, jak systém konzistentní sestavení, můžete použít pouze v prostředí s CI/CD servery, ale pro vývojové prostředí a balíčků. Například můžete připojit váš zdrojový kód do kontejneru, který má být sestaven přizpůsobené prostředí. když budete pokračovat v používání sady Visual Studio nebo jinými nástroji psát kód. Pokud váš pracovní postup CI/CD používá stejnou image kontejneru, máte jistotu, které se kód sestavil konzistentně. Kontejnery můžete použít pro modul runtime konzistence, což je běžné, že mikroslužby pomocí systému Orchestrace; více kontejnerů je ale nad rámec tohoto článku.

Pokud Visual Studio Build Tools neobsahuje nezbytné k sestavování zdrojového kódu, stejný postup lze použít pro produkty Visual Studio. Mějte na paměti, ale kontejnerů Windows, je potřeba automatizovat všechny příkazy nepodporují interaktivní uživatelské rozhraní.

## <a name="before-you-begin"></a>Před zahájením

Některé znalost [Docker](https://www.docker.com/what-docker) se předpokládá, že níže. Pokud již nejste obeznámeni s Dockerem a systémem Windows, přečtěte si informace o tom, jak [nainstalovat a nakonfigurovat modul Docker na Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/configure-docker-daemon).

Základní obrázku níže je příklad a nemusí fungovat pro váš systém. Čtení [Kompatibilita verzí kontejnerů Windows](https://docs.microsoft.com/virtualization/windowscontainers/deploy-containers/version-compatibility) Chcete-li určit, které základní image, měli byste použít pro vaše prostředí.

## <a name="create-and-build-the-dockerfile"></a>Vytvoření a vytvoření souboru Dockerfile

Uložte soubor Dockerfile v následujícím příkladu do nového souboru na disku. Pokud je soubor nazván jednoduše soubor Dockerfile"", je rozpoznán ve výchozím nastavení.

> [!WARNING]
> V tomto příkladu soubor Dockerfile vyloučí pouze starší Windows sad SDK, kterou nejde instalovat do kontejnerů. Dřívější verze způsobit selhání příkazu sestavení.

1. Otevřete příkazový řádek.

1. Vytvořte nový adresář (doporučeno):

   ```shell
   mkdir C:\BuildTools
   ```

1. Změňte adresář na tento nový adresář:

   ```shell
   cd C:\BuildTools
   ```

1. Uložte C:\BuildTools\Dockerfile následujícím obsahem.
 
   ::: moniker range="vs-2017"

   ```dockerfile
   # escape=`

   # Use the latest Windows Server Core image with .NET Framework 4.7.2.
   FROM mcr.microsoft.com/dotnet/framework/sdk:4.7.2-windowsservercore-ltsc2019

   # Restore the default Windows shell for correct batch processing.
   SHELL ["cmd", "/S", "/C"]

   # Download the Build Tools bootstrapper.
   ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe

   # Install Build Tools excluding workloads and components with known issues.
   RUN C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
       --installPath C:\BuildTools `
       --all `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
       --remove Microsoft.VisualStudio.Component.Windows81SDK `
    || IF "%ERRORLEVEL%"=="3010" EXIT 0

   # Start developer command prompt with any other commands specified.
   ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

   # Default to PowerShell if no other command specified.
   CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
   ```

   > [!WARNING]
   > Pokud základní image přímo na microsoft/windowsservercore nebo mcr.microsoft.com/windows/servercore (naleznete v tématu [syndikátní Microsoft podniky kontejneru katalogu](https://azure.microsoft.com/blog/microsoft-syndicates-container-catalog/)), nemusí správně nainstalovat rozhraní .NET Framework a je žádná chyba instalace uvedené. Po dokončení instalace nemusí spouštět spravovaný kód. Místo toho na základní image [microsoft/dotnet-framework:4.7.2](https://hub.docker.com/r/microsoft/dotnet-framework) nebo novější. Všimněte si také, že Image, které jsou označené verzí 4.7.2 nebo vyšší může pomocí prostředí PowerShell jako výchozí `SHELL`, což způsobí, že `RUN` a `ENTRYPOINT` pokyny k selhání.
   >
   > Visual Studio 2017 verze 15,8 nebo starší (libovolný produkt) se nenainstaluje správně mcr.microsoft.com/windows/servercore:1809 nebo novější. Se nezobrazí žádná chyba.
   >
   > Zobrazit [Kompatibilita verzí kontejnerů Windows](https://docs.microsoft.com/virtualization/windowscontainers/deploy-containers/version-compatibility) zobrazíte, které verze kontejneru operačního systému se podporují na hostitelském operačním systému verze, a [známé problémy pro kontejnery](build-tools-container-issues.md) známých problémů.

   ::: moniker-end

   ::: moniker range="vs-2019"

   ```dockerfile
   # escape=`

   # Use the latest Windows Server Core image with .NET Framework 4.8.
   FROM mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-ltsc2019

   # Restore the default Windows shell for correct batch processing.
   SHELL ["cmd", "/S", "/C"]

   # Download the Build Tools bootstrapper.
   ADD https://aka.ms/vs/16/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe

   # Install Build Tools excluding workloads and components with known issues.
   RUN C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
       --installPath C:\BuildTools `
       --all `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
       --remove Microsoft.VisualStudio.Component.Windows81SDK `
    || IF "%ERRORLEVEL%"=="3010" EXIT 0

   # Start developer command prompt with any other commands specified.
   ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

   # Default to PowerShell if no other command specified.
   CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
   ```

   > [!WARNING]
   > Pokud vytváříte svou image přímo na microsoft/windowsservercore, nemusí správně nainstalovat rozhraní .NET Framework a je uvedena žádná chyba instalace. Po dokončení instalace nemusí spouštět spravovaný kód. Místo toho na základní image [microsoft/dotnet-framework: 4.8](https://hub.docker.com/r/microsoft/dotnet-framework) nebo novější. Také může Všimněte si, že Image, které jsou označené verze 4,8 nebo novější pomocí Powershellu, jako výchozí `SHELL`, což způsobí, že `RUN` a `ENTRYPOINT` pokyny k selhání.
   >
   > Zobrazit [Kompatibilita verzí kontejnerů Windows](https://docs.microsoft.com/virtualization/windowscontainers/deploy-containers/version-compatibility) zobrazíte, které verze kontejneru operačního systému se podporují na hostitelském operačním systému verze, a [známé problémy pro kontejnery](build-tools-container-issues.md) známých problémů.

   ::: moniker-end

1. Spusťte následující příkaz v tomto adresáři.

   ::: moniker range="vs-2017"

   ```shell
   docker build -t buildtools2017:latest -m 2GB .
   ```

   Tento příkaz sestaví soubor Dockerfile v aktuálním adresáři pomocí 2 GB paměti. Výchozí hodnota 1 GB nestačí při instalaci některých úloh; Nicméně je možné vytvářet pouze 1 GB paměti, v závislosti na požadavcích sestavení.

   Finální image je označený "buildtools2017:latest", takže můžete snadno ji spustit v kontejneru jako "buildtools2017" od "posledního" značka je výchozí, pokud není zadána žádná značka. Pokud chcete použít konkrétní verzi sady Visual Studio vytvářet 2017 nástroje více [pokročilý scénář](advanced-build-tools-container.md), může být místo toho značku kontejneru s konkrétním Visual Studio build číslo stejně jako "posledního", tak kontejnery lze použít konkrétní verze konzistentně.

   ::: moniker-end

   ::: moniker range="vs-2019"

   ```shell
   docker build -t buildtools2019:latest -m 2GB .
   ```

   Tento příkaz sestaví soubor Dockerfile v aktuálním adresáři pomocí 2 GB paměti. Výchozí hodnota 1 GB nestačí při instalaci některých úloh; Nicméně je možné vytvářet pouze 1 GB paměti, v závislosti na požadavcích sestavení.

   Finální image je označený "buildtools2019:latest", takže můžete snadno ji spustit v kontejneru jako "buildtools2019" od "posledního" značka je výchozí, pokud není zadána žádná značka. Pokud chcete použít konkrétní verzi sady Visual Studio vytvářet 2019 nástroje více [pokročilý scénář](advanced-build-tools-container.md), může být místo toho značku kontejneru s konkrétním Visual Studio build číslo stejně jako "posledního", tak kontejnery lze použít konkrétní verze konzistentně.

   ::: moniker-end

## <a name="using-the-built-image"></a>Pomocí sestavenou image

Teď, když jste vytvořili image, můžete ji spustit v kontejneru provádět interaktivní a automatizované sestavování. V příkladu se používá Developer Command Prompt, takže vaše cesta i ostatním proměnným prostředí jsou už nakonfigurovaná.

1. Otevřete příkazový řádek.

1. Spuštění kontejneru začínat prostředí PowerShell pro všechny vývojáře nastavení proměnné prostředí:

   ::: moniker range="vs-2017"

   ```shell
   docker run -it buildtools2017
   ```

   ::: moniker-end

   ::: moniker range="vs-2019"

   ```shell
   docker run -it buildtools2019
   ```

   ::: moniker-end

Pokud chcete použít tuto bitovou kopii pro pracovní postup CI/CD, je možné ji publikovat na vlastní [Azure Container Registry](https://azure.microsoft.com/services/container-registry) nebo jiných interní [registru Dockeru](https://docs.docker.com/registry/deploying) tak servery potřebují jenom chcete stáhnout.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Rozšířený příklad pro kontejnery](advanced-build-tools-container.md)
* [Známé problémy s kontejnery](build-tools-container-issues.md)
* [ID pracovního vytížení a komponenta Visual Studio Build Tools](workload-component-id-vs-build-tools.md)
