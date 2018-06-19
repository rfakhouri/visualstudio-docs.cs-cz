---
title: Šablona projektu Azure cloud service pro jazyk Python
description: Přehled šablony sady Visual Studio pro cloudové služby Azure napsané v Pythonu včetně nasazení role, závislosti a řešení potíží.
ms.date: 07/13/2017
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 42b2cf1fda241e178804847d86e6af9e4f33e7bd
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031810"
---
# <a name="azure-cloud-service-projects-for-python"></a>Projekty Azure cloudových služeb pro jazyk Python

Visual Studio poskytuje šablony vám pomohou začít vytvářet Azure Cloud Services používá Python.

A [Cloudová služba](https://docs.microsoft.com/azure/cloud-services/) se skládá z libovolného počtu *rolí pracovního procesu* a *webové role*, z nichž každá provádí koncepčně samostatná úloha, ale můžete samostatně replikaci podle potřeby pro škálování virtuálních počítačů. Webové role poskytují hostování pro front-end webové aplikace. Python jsou obavy, všechny webové rozhraní, které podporuje WSGI můžete použít pro zapsání takové aplikace (podporuje [šablona projektu webové](python-web-application-project-templates.md)). Role pracovního procesu jsou určeny k dlouho běžící procesy, které není komunikovat přímo s uživateli. Obvykle provádění pomocí balíčků v balíčku "azure", který se instaluje s [ `pip install azure` ](http://pypi.org/project/azure).

Tento článek obsahuje podrobné informace o šabloně projektů a další podporu Visual Studio 2017 (starší verze jsou podobné, ale některé rozdíly). Další informace o práci s Azure z Python, přejděte [Azure střediska pro vývojáře Python](https://docs.microsoft.com/en-us/python/azure/?view=azure-python).

## <a name="create-a-project"></a>Vytvoření projektu

1. Nainstalujte [.NET SDK služby Azure pro sadu Visual Studio](https://www.visualstudio.com/vs/azure-tools/), které je potřeba použít šablonu služby cloudu.
1. V sadě Visual Studio, vyberte **soubor > Nový > projekt...** , vyhledejte "Azure Python" a vyberte **Azure Cloud Service** ze seznamu:

    ![Šablona projektu cloudové Azure pro jazyk Python](media/template-azure-cloud-project.png)

1. Vyberte jednu nebo více rolí, které chcete zahrnout. Projekty cloudových může kombinovat role zapisují v různých jazycích, takže můžete snadno napsat jednotlivých součástí aplikace v jazyce nejvhodnější. Chcete-li po dokončení toto dialogové okno Přidat nové role do projektu, klikněte pravým tlačítkem **role** v Průzkumníku řešení a výběrem jedné z položek v části **přidat**.

    ![Přidávání rolí v šabloně projektu Azure Cloud](media/template-azure-cloud-service-project-wizard.png)

1. Projekty jednotlivé role vytvářené, zobrazí se výzva k instalaci další balíčky Python, jako je například rozhraní Django a Bottle, Flask, pokud jste vybrali roli, která používá jednu z nich.

1. Po přidání nové role do projektu, se zobrazí pokyny ke konfiguraci. Změny konfigurace jsou obvykle není zapotřebí, ale může být užitečná pro budoucí přizpůsobení vašich projektů. Všimněte si, že při přidávání více rolí ve stejnou dobu, zůstane otevřená jenom pokyny pro poslední role. Ale najdete pokyny a tipy k řešení potíží pro jiné role v jejich odpovídajících `readme.mht` soubory, které jsou umístěné v kořenové role nebo v `bin` složky.

1. Projektu `bin` složka také obsahuje jednu nebo dvě skriptů prostředí PowerShell, které se používají ke konfiguraci vzdáleného virtuálního počítače, včetně instalace Python, všechny [requirements.txt](#dependencies) souborů ve vašem projektu a nastavení služby IIS, pokud nezbytné. Může upravit tyto soubory podle potřeby pro vaše nasazení, i když nejběžnější možnosti se dají spravovat další způsoby (viz [konfigurace nasazení role](#configuring-role-deployment) níže). Není doporučujeme odebrat tyto soubory jako skript starší verzi konfigurace bude místo něj použita, pokud nejsou soubory k dispozici.

    ![Soubory podpory Role pracovního procesu](media/template-azure-cloud-service-worker-role-support-files.png)

    Chcete-li přidat tyto konfigurační skripty na nový projekt, klikněte pravým tlačítkem na projekt, vyberte možnost **Přidat > novou položku...** a vyberte buď **webové Role podpůrné soubory** nebo **soubory podpory Role pracovního procesu**.

## <a name="configuring-role-deployment"></a>Konfigurace nasazení role

Skripty prostředí PowerShell v projekt role `bin` složky řízení nasazení této role a může být upravit k přizpůsobení konfigurace:

- `ConfigureCloudService.ps1` je obvykle se používá pro webové a pracovní role nainstalovat a nakonfigurovat závislosti a nastavte verzi jazyka Python.
- `LaunchWorker.ps1` se používá pouze pro role pracovního procesu a slouží k změnit chování při spuštění, přidejte argumenty příkazového řádku nebo přidat proměnné prostředí.

Oba soubory obsahují pokyny pro přizpůsobení. Můžete také nainstalovat vlastní verzi jazyka Python přidáním jiná úloha do projektu hlavní cloudové služby `ServiceDefinition.csdef` nastavení souboru `PYTHON` proměnnou jeho nainstalované `python.exe` (nebo ekvivalentního) cestu. Když `PYTHON` je nastavena, Python není nainstalována z NuGet.

Další konfigurace se dá udělat následujícím způsobem:

1. Instalovat balíčky pomocí `pip` aktualizací `requirements.txt` soubor v kořenovém adresáři projektu. `ConfigureCloudService.ps1` Skript nainstaluje tento soubor na nasazení.
1. Nastavení proměnných prostředí změnou vaše `web.config` souboru (webové role) nebo `Runtime` část vaší `ServiceDefinition.csdef` souboru (role pracovního procesu).
1. Zadejte skript a argumenty, které mají použít pro roli pracovního procesu změnou příkazového řádku v `Runtime/EntryPoint` část vaší `ServiceDefinitions.csdef` souboru.
1. Nastavte hlavní obslužná rutina skriptu pro webovou roli prostřednictvím `web.config` souboru.

## <a name="testing-role-deployment"></a>Testování nasazení role

Při zápisu role, můžete otestovat projektu cloudové místně pomocí emulátoru služby v cloudu. Emulátor je součástí sady SDK nástroje Azure a je omezený verzi prostředí používá při publikování cloudové služby Azure.

Pokud chcete spustit v emulátoru, nejdříve se ujistěte, projektu cloudu je projekt po spuštění ve vašem řešení pravým tlačítkem myši a výběrem **nastavit jako spouštěný projekt**. Potom vyberte **ladění > Spustit ladění** (F5) nebo **ladění > Spustit bez ladění** (Ctrl + F5).

Všimněte si, že z důvodu omezení v emulátoru není možné ladit kód Python. Proto doporučujeme ladění role je spuštěním nezávisle a potom pomocí emulátoru integrace testování před publikováním.

## <a name="deploying-a-role"></a>Nasazení role

Chcete-li otevřít **publikovat** průvodce, vyberte roli projekt v Průzkumníku řešení a vyberte **sestavení > Publikovat** z hlavní nabídky, nebo klikněte pravým tlačítkem na projekt a vyberte **publikovat**.

Proces publikování zahrnuje dvě fáze. První Visual Studio vytvoří jeden balíček obsahující všechny role pro cloudové služby. Tento balíček je, co je nasazen do Azure, která inicializuje jeden nebo více virtuálních počítačů pro každou roli a nasadit zdroj.

Protože každý virtuální počítač se aktivuje, provede `ConfigureCloudService.ps1` skript a nainstalujte všechny závislosti. Tento skript ve výchozím nastavení nainstaluje nejnovější verzi jazyka Python z [NuGet](https://www.nuget.org/packages?q=Tags%3A%22python%22+Authors%3A%22Python+Software+Foundation%22) a všechny balíčky v zadané `requirements.txt` souboru.

Nakonec spuštěním rolí pracovního procesu `LaunchWorker.ps1`, který spuštěn skript v jazyce Python; webové role inicializovat služby IIS a zahájení zpracování webových požadavků.

## <a name="dependencies"></a>Závislosti

Pro cloudové služby `ConfigureCloudService.ps1` skript používá `pip` nainstalovat sadu Python závislosti. Závislosti musí být zadán v souboru s názvem `requirements.txt` (přizpůsobit úpravou `ConfigureCloudService.ps1`). Soubor je spuštěn s `pip install -r requirements.txt` během inicializace.

Poznámka: instance cloudové služby, musíte zadat všechny knihovny s příponami C nezahrnují kompilátory jazyka C předem zkompilovat binární soubory.

PIP a jeho závislosti, jakož i balíčky v `requirements.txt`, se stáhnou automaticky a může se počítají jako využití fakturovatelné šířky pásma. V tématu [Správa požadované balíčky](managing-required-packages-with-requirements-txt.md) podrobnosti o správě `requirements.txt` soubory.

## <a name="troubleshooting"></a>Poradce při potížích

Pokud váš web nebo worker role tak správně, po nasazení, zkontrolujte následující:

- Složka bin\ s zahrnuje projekt Python (aspoň):

  - `ConfigureCloudService.ps1`
  - `LaunchWorker.ps1` (pro role pracovního procesu)
  - `ps.cmd`

- Zahrnuje projekt Python `requirements.txt` souborů, výpis všechny závislosti (nebo případně kolekce souborů kolečko).
- Povolení vzdálené plochy na cloudové služby a prozkoumejte soubory protokolu.
- Protokoly pro `ConfigureCloudService.ps1` a `LaunchWorker.ps1` jsou uloženy v `C:\Resources\Directory\%RoleId%.DiagnosticStore\LogFiles` složky na vzdáleném počítači.
- Webové role může zapisovat další protokoly nakonfigurována v cesta k `web.config`, konkrétně cest `WSGI_LOG` appSetting. Funguje taky nejvíce regulární protokolování služby IIS nebo FastCGI.
- V současné době `LaunchWorker.ps1.log` soubor je jediný způsob, jak zobrazit výstup nebo chyby zobrazené ve své role pracovního procesu Python.