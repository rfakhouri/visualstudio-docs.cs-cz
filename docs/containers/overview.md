---
title: Nástroje kontejneru sady Visual Studio na Windows
description: Poznejte k dispozici v sadě Visual Studio tools pro práci s Dockerem
author: ghogen
ms.author: ghogen
ms.topic: overview
ms.date: 03/20/2019
ms.technology: vs-azure
ms.openlocfilehash: 4b03ccddadf954b8430b7ad9b5a4ed765fccc3f5
ms.sourcegitcommit: cd91a8a4f6086cda9ba6948be25864fc7d6b8e44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/12/2019
ms.locfileid: "59537970"
---
# <a name="container-tools-in-visual-studio"></a>Nástroje kontejneru sady Visual Studio

Nástroje v sadě Visual Studio pro vývoj s využitím kontejnerů se snadno používá a výrazně zjednodušuje tvorbu, ladění a nasazování kontejnerizovaných aplikací. Můžete pracovat jako kontejner pro jeden projekt, nebo pomocí Orchestrace kontejnerů pomocí Docker Compose, Service Fabric nebo Kubernetes pracovat s více službami v kontejnerech.

> [!NOTE]
> Tento článek se týká sady Visual Studio ve Windows a ne Visual Studio pro Mac.

> [!TIP]
> Další informace o instalaci Dockeru pro Windows najdete v tématu [Desktop Docker pro Windows](https://docs.docker.com/docker-for-windows/).

## <a name="docker-support-in-visual-studio"></a>Podpora dockeru v sadě Visual Studio

Podporu dockeru je k dispozici pro některé typy projektů .NET.  Je k dispozici pro projekty ASP.NET, ASP.NET Core projekty a projekty konzoly .NET Core a .NET Framework.

Podpora pro Docker v sadě Visual Studio změnilo několik verzí v reakci na požadavky zákazníků. Existují dvě úrovně podpory Dockeru, které můžete přidat do projektu a podporované možnosti se liší podle typu projektu a verzi sady Visual Studio. U některých typů podporovaných projektu Pokud chcete kontejner pro jeden projekt, bez použití orchestraci, Uděláte to tak, že přidáte podporu Dockeru.  Další úrovní je podporu Orchestrace kontejnerů, která přidá odpovídající podpůrné soubory pro konkrétní orchestrátoru, který zvolíte.  

::: moniker range="vs-2017"

Pomocí sady Visual Studio 2017 můžete použít jako služeb Orchestrace kontejnerů Docker Compose a Service Fabric.  Můžete také použít Kubernetes, pokud nainstalujete [Visual Studio Tools pro systém Kubernetes](https://aka.ms/get-vsk8stools).

> [!NOTE]
> Pokud používáte verzi sady Visual Studio 2017 před 15.8 nebo použijete šablony projektů rozhraní .NET Framework (ne .NET Core), pokud chcete přidat podporu Dockeru, je automaticky přidána podpora Orchestrace pomocí Docker Compose. Podpora Orchestrace kontejnerů pomocí Docker Compose, je automaticky přidán v sadě Visual Studio 2017 verze 15.0: 15.7 a pro projekty .NET Framework.

::: moniker-end

::: moniker range=">=vs-2019"

S Visual Studio 2019 můžete použít jako služeb Orchestrace kontejnerů Docker Compose, Kubernetes a Service Fabric.

> [!NOTE]
> Pokud používáte úplné rozhraní .NET Framework konzoly šablony projektu, když přidáte podporu Dockeru, je automaticky přidána podpora pro orchestraci pomocí Docker Compose.
::: moniker-end

**Přidat > Podpora Dockeru** a **Přidat > Podpora Orchestrátoru kontejnerů** příkazy jsou umístěné v místní nabídce (nebo kontextovou nabídku) uzel projektu pro projekt ASP.NET Core v  **Průzkumník řešení**, jak je znázorněno na následujícím snímku obrazovky:

![Přidejte podporu Dockeru nabídky v sadě Visual Studio](./media/overview/add-docker-support-menu.png)

### <a name="adding-docker-support-without-orchestration"></a>Přidání podpory Dockeru (bez Orchestrace)

Můžete přidat podporu Dockeru do existujícího projektu tak, že vyberete **přidat** > **podporu Dockeru** v **Průzkumníka řešení**. Můžete také povolit podporu Dockeru během vytváření projektu tak, že vyberete **povolit podporu Dockeru** při vytváření nového projektu, jak je znázorněno na následujícím snímku obrazovky:

::: moniker range="vs-2017"
![Povolit podporu Dockeru pro novou webovou aplikaci ASP.NET Core v sadě Visual Studio](./media/overview/enable-docker-support-visual-studio.png)
::: moniker-end
::: moniker range=">=vs-2019"
![Povolit podporu Dockeru pro novou webovou aplikaci ASP.NET Core v sadě Visual Studio](./media/overview/vs-2019/enable-docker-support-visual-studio.png)
::: moniker-end

Když přidáváte nebo povolit podporu Dockeru, Visual Studio přidá do projektu následující:

- *soubor Dockerfile* souboru
- soubor .dockerignore
- odkaz na balíček NuGet do Microsoft.VisualStudio.Azure.Containers.Tools.Targets

::: moniker range=">=vs-2019"
Řešení se po přidání podpory Dockeru vypadá například takto:

![Snímek obrazovky Průzkumníka řešení se souborem Dockerfile a .dockerignore](media/overview/vs-2019/dockerfile-dockerignore.png)
::: moniker-end

::: moniker range="vs-2017"
> [!NOTE]
> Když povolit podporu Dockeru během vytváření projektu pro projekt ASP.NET (.NET Framework, ne k projektu .NET Core), jak je znázorněno na následujícím snímku obrazovky, přidá se také podpora Orchestrace kontejnerů.

![Povolit Docker compose podporu pro technologie ASP.NET](media/overview/enable-docker-compose-support.png)
::: moniker-end

## <a name="docker-compose-support"></a>Podpora docker Compose

Pokud chcete vytvořit řešení více kontejnerů pomocí Docker Compose, přidáte do vašich projektů podpora Orchestrace kontejnerů. To vám umožní spouštět a ladit skupinu kontejnerů (celé řešení nebo skupinu projektů) ve stejnou dobu, pokud jsou definovány ve stejném *docker-compose.yml* souboru.

Chcete-li přidat podporu Orchestrace kontejnerů pomocí Docker Compose, klikněte pravým tlačítkem na uzel řešení nebo projektu v **Průzkumníku řešení**a zvolte **Přidat > Podpora Orchestrace kontejnerů**. Klikněte na tlačítko **Docker Compose** Spravovat kontejnery.

Když přidáte do projektu podporu Orchestrace kontejnerů, zobrazí se *soubor Dockerfile* přidány do projektu (pokud existuje nenašli jste jednu již) a **docker-compose** složky přidán do řešení v  **Průzkumník řešení**, jak je znázorněno zde:

![Soubory docker v Průzkumníku řešení v sadě Visual Studio](media/overview/docker-support-solution-explorer.png)

Pokud *docker-compose.yml* již existuje, požadovaných řádků kódu, konfigurace sady Visual Studio právě přidá k němu.

Postupujte stejně jako s projekty, které chcete kontrolovat pomocí Docker Compose.

## <a name="kubernetes-support"></a>Podpora pro Kubernetes

::: moniker range="vs-2017"
Chcete-li přidat podporu Kubernetes, nainstalujte [Visual Studio Tools pro systém Kubernetes](https://aka.ms/get-vsk8stools).
::: moniker-end

Díky podpoře Kubernetes, můžete povolit připojení mezi místní projekt a clusterů Kubernetes spuštěných [Azure Kubernetes Service (AKS)](/azure/aks)a tím upravovat a ladit vaše služby spuštěné ve službě AKS pomocí sady Visual Studio.  Tato služba je poskytovaná [Azure Dev prostory](/azure/dev-spaces/quickstart-netcore-visualstudio). Azure Dev prostory také budete moct nastavit samostatných větvích vaší služby Kubernetes s názvem *dev prostory* pro účely vývoje, tak můžete efektivně izolovat produkční služby z pracovní verze ve vývoji a zachovat různé úpravy jasně oddělen od sebe navzájem.

Chcete-li přidat podporu Kubernetes do vašich projektů, zvolte **Kubernetes a Helm** když přidáte podporu Orchestrace kontejnerů. Několik souborů jsou přidány do projektu, včetně *azds.yaml*, které konfiguruje Azure Dev mezery a grafy Helm, které popisují strukturu vašich služeb Kubernetes.

## <a name="service-fabric-support"></a>Podpora Service Fabric

Pomocí nástroje Service Fabric v sadě Visual Studio vývoj a ladění pro Azure Service Fabric, spouštět a ladit lokálně a nasazení do Azure.

::: moniker range="vs-2017"
Visual Studio 2017 verze 15.9 nebo novější s nainstalovaná úloha vývoj pro Azure podporuje vývoj kontejnerizovaných mikroslužeb a využívající kontejnery Windows a Orchestrace Service Fabric.
::: moniker-end
::: moniker range=">=vs-2019"
Visual Studio 2019 podporuje vývoj kontejnerizované mikroslužby a využívající kontejnery Windows a Orchestrace Service Fabric.
::: moniker-end

Podrobný kurz najdete v tématu [kurzu: Nasazení aplikace .NET v kontejneru Windows do Azure Service Fabric](/azure/service-fabric/service-fabric-host-app-in-a-container).

Další informace o Azure Service Fabric najdete v tématu [Service Fabric](/azure/service-fabric).

## <a name="continuous-delivery-and-continuous-integration-cicd"></a>Průběžné doručování a průběžnou integraci (CI/CD)

Visual Studio snadno integrovat Azure kanály pro automatizované a průběžná integrace a doručování změn do kódu služby a konfiguraci. Abyste mohli začít, najdete v článku [vytvořit svůj první kanál](/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=tfs-2018-2).

Service Fabric najdete v části [kurzu: Nasazení aplikace ASP.NET Core do Azure Service Fabric pomocí projektů Azure DevOps](/azure/devops-project/azure-devops-project-service-fabric).

Kubernetes, naleznete v tématu [nasazení aplikace typu kontejner Dockeru do služby Azure Kubernetes Service](/azure/devops/pipelines/apps/cd/deploy-aks?view=azure-devops).

## <a name="next-steps"></a>Další kroky

Další podrobnosti o službách implementaci a použití sady Visual Studio tools pro práci s kontejnery, v následujících článcích:

[Ladění aplikací v místním kontejneru Dockeru](vs-azure-tools-docker-edit-and-refresh.md)

[Nasazení kontejneru ASP.NET do služby container registry pomocí sady Visual Studio](vs-azure-tools-docker-hosting-web-apps-in-docker.md)
