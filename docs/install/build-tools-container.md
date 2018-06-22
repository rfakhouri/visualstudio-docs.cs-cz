---
title: Instalace sestavení nástroje sady Visual Studio do kontejneru
description: Informace o instalaci nástrojů Visual Studio sestavení do kontejneru systému Windows pro podporu průběžnou integraci a pracovních postupů nastavené průběžné doručování (CI/CD).
ms.custom: ''
ms.date: 04/18/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: d5c038e2-e70d-411e-950c-8a54917b578a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47657cd7b9521de365fb02202714a708a4c4c3f5
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282356"
---
# <a name="install-build-tools-into-a-container"></a>Instalace nástroje sestavení do kontejneru

Sestavení nástroje sady Visual Studio můžete nainstalovat do kontejneru systému Windows pro podporu průběžnou integraci a pracovních postupů nastavené průběžné doručování (CI/CD). Tento článek vás provede jaké Docker změny konfigurace jsou požadovány a co [úlohy a součásti](workload-component-id-vs-build-tools.md) můžete nainstalovat v kontejneru.

[Kontejnery](https://www.docker.com/what-container) jsou skvělý způsob, jak můžete použít pouze v prostředí serverů CI/CD, ale pro vývojové prostředí také systému konzistentní sestavení balíčku. Například můžete připojit vašeho zdrojového kódu do kontejneru, který má být sestaven přizpůsobené prostředí, zatímco stále zápis kódu pomocí sady Visual Studio nebo jiných nástrojů. Pokud pracovní postup CI/CD používá stejnou bitovou kopii kontejneru, umístění jistotu, že váš kód sestavení konzistentně. Kontejnery můžete použít pro modul runtime rovněž konzistenci, což je běžný u micro-services pomocí několika kontejnerů systémem orchestration; je však nad rámec tohoto článku.

Pokud Visual Studio Tools sestavení nemá co potřebujete k vytvoření vašeho zdrojového kódu, stejný postup lze pro ostatní produkty Visual Studio. Upozorňujeme však, kontejnery Windows, musí být všechny příkazy automatizované nepodporují interaktivní uživatelské rozhraní.

## <a name="overview"></a>Přehled

Pomocí [Docker](https://www.docker.com/what-docker) vytvoření bitové kopie ze kterého můžete vytvořit kontejnery, které sestavení vašeho zdrojového kódu. V příkladu soubor Docker nainstaluje nejnovější Visual Studio sestavení nástroje 2017 a některé další užitečné programy často používá pro vytváření zdrojového kódu. Dále můžete upravit vlastní soubor Docker zahrnout další nástroje a skripty, které testy, publikovat sestavení výstup a další.

Pokud jste již nainstalovali Docker pro systém Windows, můžete přeskočit ke kroku 3.

## <a name="step-1-enable-hyper-v"></a>Krok 1. Povolení technologie Hyper-V

Technologie Hyper-V není povolena ve výchozím nastavení. Musí být povoleno spustit Docker pro systém Windows, od aktuálně je podporována pouze izolace technologie Hyper-V pro Windows 10.

* [Povolení technologie Hyper-V v systému Windows 10](https://docs.microsoft.com/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v)
* [Povolení technologie Hyper-V v systému Windows Server 2016](https://docs.microsoft.com/windows-server/virtualization/hyper-v/get-started/install-the-hyper-v-role-on-windows-server)

> [!NOTE]
> Na počítači musí být povolena virtualizace. Obvykle je povolena ve výchozím nastavení; ale pokud se nepovede instalaci technologie Hyper-V, naleznete v dokumentaci k systému pro povolení virtualizace.

## <a name="step-2-install-docker-for-windows"></a>Krok 2. Nainstalujte Docker pro Windows

Pokud používáte Windows 10, můžete [stáhněte a nainstalujte Docker Community Edition](https://docs.docker.com/docker-for-windows/install). Pokud používáte systém Windows Server 2016, postupujte podle [pokyny pro instalaci edice Enterprise Docker](https://docs.docker.com/install/windows/docker-ee).

## <a name="step-3-switch-to-windows-containers"></a>Krok 3. Přepnout na Windows kontejnery

2017 nástroje pro sestavení můžete nainstalovat pouze na systému Windows, který vyžaduje, abyste [přepnout do kontejnerů Windows](https://docs.docker.com/docker-for-windows/#getting-started-with-windows-containers). Kontejnery Windows ve Windows 10 podporují pouze [technologie Hyper-V izolaci](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container), zatímco Windows kontejnerů v systému Windows Server 2016 podporu obou technologie Hyper-V a izolaci procesu.

## <a name="step-4-expand-maximum-container-disk-size"></a>Krok 4. Rozbalte kontejner maximální velikost disku

Visual Studio nástroje - sestavení a ve větší míře Visual Studio – vyžadovat velké množství místa na disku pro všechny nástroje, které budou instalovány. I když například soubor Docker zakážete mezipaměť balíčku, velikost disku kontejner imagí musí skutečnost zohlednit zvýšením požadované místo. Aktuálně v systému Windows, můžete pouze zvýšit velikost disku změnou konfigurace Docker.

**V systému Windows 10**:

1. [Rick, klikněte na ikonu Docker pro systém Windows](https://docs.docker.com/docker-for-windows/#docker-settings) na hlavním panelu a klikněte na **nastavení...** .
2. [Klikněte na démon](https://docs.docker.com/docker-for-windows/#docker-daemon) části.
3. [Přepnutí **základní** ](https://docs.docker.com/docker-for-windows/#edit-the-daemon-configuration-file) tlačítko pro **Upřesnit**.
4. Přidejte následující pole JSON vlastnost zvýšit místa na disku pro 120 GB (víc než dost pro nástroje sestavení s místo pro růst).

   ```json
   {
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

   Tato vlastnost se přidá do nic, co už máte. Například se tyto změny budou použity k výchozí démon konfigurační soubor, měli byste vidět:

   ```json
   {
     "registry-mirrors": [],
     "insecure-registries": [],
     "debug": true,
     "experimental": true,
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

5. Klikněte na tlačítko **použít**.

**V systému Windows Server 2016**:

1. Zastavte službu "docker":

   ```shell
   sc.exe stop docker
   ```

2. Z příkazového řádku se zvýšenými oprávněními upravit "% ProgramData%\Docker\config\daemon.json" (nebo ať zadali `dockerd --config-file`).
3. Přidejte následující pole JSON vlastnost zvýšit místa na disku pro 120 GB (víc než dost pro nástroje sestavení s místo pro růst).

   ```json
   {
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

   Tato vlastnost se přidá do nic, co už máte.
4. Soubor uložte a zavřete.
5. Spusťte službu "docker":

   ```shell
   sc.exe start docker
   ```

## <a name="step-5-create-and-build-the-dockerfile"></a>Krok 5. Vytvořte a sestavte soubor Docker

Uložte soubor Docker v následujícím příkladu do nového souboru na disku. Pokud je soubor jednoduše soubor Docker"", uznává se ve výchozím nastavení.

> [!NOTE]
> Tento příklad soubor Docker pouze vyloučí starší Windows SDK, která se nedá nainstalovat do kontejnerů. Starší verze způsobit selhání příkazu sestavení.

1. Otevřete příkazový řádek.
2. Vytvořte nový adresář (doporučeno):

   ```shell
   mkdir C:\BuildTools
   ```

3. Změňte adresáře na tento nový adresář:

   ```shell
   cd C:\BuildTools
   ```

3. Uložte C:\BuildTools\Dockerfile následující obsah.

   ```dockerfile
   # escape=`

   # Use the latest Windows Server Core image with .NET Framework 4.7.1.
   FROM microsoft/dotnet-framework:4.7.1

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

   > [!NOTE]
   > Pokud vytváříte bitové kopie přímo na microsoft/windowsservercore, nemusí být správně nainstalovány rozhraní .NET Framework a není instalace oznámena chyba. Spravovaný kód nemusí spustit po dokončení instalace. Místo toho základní bitové kopie na [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) nebo novější.

4. Spusťte následující příkaz v tomto adresáři.

   ```shell
   docker build -t buildtools2017:latest -m 2GB .
   ```

   Tento příkaz vytvoří soubor Docker v aktuálním adresáři pomocí 2 GB paměti. Výchozí hodnota 1 GB není dostatečná při instalaci některé úlohy; ale nebudete moct sestavení s pouze 1 GB paměti, v závislosti na své požadavky na sestavení

   Finální image je s příznakem "buildtools2017:latest", takže můžete snadno ji spustit v kontejneru jako "buildtools2017" od "posledního" značky je výchozím nastavením, pokud je zadána žádná značka. Pokud chcete použít konkrétní verzi nástroje Visual Studio sestavení 2017 nástroje ve více [pokročilé scénáře](advanced-build-tools-container.md), můžete místo toho může označit kontejneru s konkrétní sady Visual Studio sestavení číslo a také "posledního", takže kontejnery můžete použít konkrétní verze konzistentně.

## <a name="step-6-using-the-built-image"></a>Krok 6. Pomocí předdefinovaných bitové kopie

Teď, když jste vytvořili bitovou kopii, můžete ho spustit v kontejneru udělat interaktivní a automatizované sestavení. V příkladu příkazového řádku vývojáře, takže CESTU a jiné proměnné prostředí jsou již nakonfigurována.

1. Otevřete příkazový řádek.
2. Spusťte kontejner, aby prostředí PowerShell začínat všechny vývojáře proměnným prostředí nastaveným:

   ```shell
   docker run -it buildtools2017
   ```

Pokud chcete použít tuto bitovou kopii pro pracovní postup CI/CD, můžete ji publikujete do vlastní [registru kontejner Azure](https://azure.microsoft.com/services/container-registry) nebo jiné interní [Docker registru](https://docs.docker.com/registry/deploying) tak servery stačí ho vyžádat.

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://visualstudio.microsoft.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také:

* [Rozšířený příklad pro kontejnery](advanced-build-tools-container.md)
* [Známé problémy s kontejnery](build-tools-container-issues.md)
* [ID úlohy a součást Visual Studio 2017 nástroje pro sestavení](workload-component-id-vs-build-tools.md)
