---
title: Visual Studio Tools for Docker ve Windows
description: Seznámení s nástroji Dockeru k dispozici v sadě Visual Studio
author: ghogen
ms.author: ghogen
ms.date: 03/20/2019
ms.technology: vs-azure
ms.openlocfilehash: 68364384a233defeb69203ed4f3ddc8f122e8bb7
ms.sourcegitcommit: 3201da3499051768ab59f492699a9049cbc5c3c6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356295"
---
# <a name="docker-in-visual-studio-on-windows"></a>Docker v sadě Visual Studio ve Windows

::: moniker range="vs-2017"
Nástroje v sadě Visual Studio pro vývoj s využitím kontejnerů se snadno používá a výrazně usnadňuje sestavování, spouštění a vytvořit úkolů. Můžete také spustit a ladit své kontejnery pomocí obvyklého **F5** a **Ctrl**+**F5** klíče ze sady Visual Studio. Můžete dokonce i ladění celé řešení, pokud jeho kontejnery jsou definovány ve stejném *docker-compose.yml* souboru na úrovni řešení.
::: moniker-end
::: moniker range=">=vs-2019"
Nástroje sady Visual Studio 2019 pro vývoj s využitím kontejnerů se snadno používá a výrazně usnadňuje sestavování, spouštění a vytvořit úkolů. Můžete také spustit a ladit své kontejnery pomocí obvyklého **F5** a **Ctrl**+**F5** klíče ze sady Visual Studio. Můžete dokonce i ladění celé řešení, pokud jeho kontejnery jsou definovány ve stejném *docker-compose.yml* souboru na úrovni řešení.
::: moniker-end

> [!NOTE]
> Tento článek se týká sady Visual Studio ve Windows a ne Visual Studio pro Mac.

> [!TIP]
> Další informace o instalaci Dockeru pro Windows najdete v tématu [Desktop Docker pro Windows](https://docs.docker.com/docker-for-windows/).

## <a name="docker-support-in-visual-studio"></a>Podpora dockeru v sadě Visual Studio

::: moniker range="vs-2017"
Existují dvě úrovně podpory Dockeru, které můžete přidat do projektu. V projektech ASP.NET Core, lze přidat *soubor Dockerfile* soubor do projektu povolení podpory Dockeru. Další úrovní je podpora Orchestrace kontejnerů, které přidává *soubor Dockerfile* do projektu (pokud ještě neexistuje) a *docker-compose.yml* souboru na úrovni řešení. Podpora Orchestrace kontejnerů pomocí Docker Compose, se přidá ve výchozím nastavení v sadě Visual Studio 2017 verze 15.0: 15.7. Podpora Orchestrace kontejnerů se funkci opt-in Visual Studio 2017 verze 15,8 nebo novější. Verze 15,8 a novější podporují Docker Compose a Service Fabric.
::: moniker-end
::: moniker range=">=vs-2019"
Existují dvě úrovně podpory Dockeru, které můžete přidat do projektu. V projektech ASP.NET Core, lze přidat *soubor Dockerfile* soubor do projektu povolení podpory Dockeru. Další úrovní je podpora Orchestrace kontejnerů, které přidává *soubor Dockerfile* do projektu (pokud ještě neexistuje) a *docker-compose.yml* souboru na úrovni řešení.  Podpora Orchestrace kontejnerů je volitelná funkce v aplikaci Visual Studio 2019, který podporuje Docker Compose, Kubernetes a Service Fabric.
::: moniker-end

**Přidat > Podpora Dockeru** a **Přidat > Podpora Orchestrátoru kontejnerů** příkazy jsou umístěné v místní nabídce (nebo kontextovou nabídku) uzel projektu pro projekt ASP.NET Core v  **Průzkumník řešení**, jak je znázorněno na následujícím snímku obrazovky:

![Přidejte podporu Dockeru nabídky v sadě Visual Studio](./media/visual-studio-tools-for-docker/add-docker-support-menu.png)

### <a name="add-docker-support"></a>Přidání podpory Dockeru

Můžete přidat podporu Dockeru do existujícího projektu ASP.NET Core tak, že vyberete **přidat** > **podporu Dockeru** v **Průzkumníka řešení**. Můžete také povolit podporu Dockeru během vytváření projektu tak, že vyberete **povolit podporu Dockeru** v **nová webová aplikace ASP.NET Core** dialogové okno, které se otevře po kliknutí na **OK** v **nový projekt** dialogové okno, jak je znázorněno na následujícím snímku obrazovky.

::: moniker range="vs-2017"
![Povolit podporu Dockeru pro novou webovou aplikaci ASP.NET Core v sadě Visual Studio](./media/visual-studio-tools-for-docker/enable-docker-support-visual-studio.png)
::: moniker-end
::: moniker range=">=vs-2019"
![Povolit podporu Dockeru pro novou webovou aplikaci ASP.NET Core v sadě Visual Studio](./media/visual-studio-tools-for-docker/vs-2019/enable-docker-support-visual-studio.png)
::: moniker-end

Když přidáváte nebo povolit podporu Dockeru, sada Visual Studio přidá *soubor Dockerfile* soubor do projektu.

::: moniker range="vs-2017"
> [!NOTE]
> Když povolíte podporu Docker Compose během vytváření projektu pro projekt ASP.NET (.NET Framework, ne k projektu .NET Core), jak je znázorněno na následujícím snímku obrazovky, přidá se také podpora Orchestrace kontejnerů.

![Povolit Docker compose podporu pro technologie ASP.NET](media/visual-studio-tools-for-docker/enable-docker-compose-support.png)
::: moniker-end

### <a name="add-container-orchestration-support"></a>Přidat podporu Orchestrace kontejnerů

Pokud chcete vytvořit řešení více kontejnerů, přidáte do vašich projektů podpora Orchestrace kontejnerů. To vám umožní spouštět a ladit skupinu kontejnerů (celé řešení) ve stejnou dobu, pokud jsou definovány ve stejném *docker-compose.yml* souboru.

Chcete-li přidat podporu Orchestrace kontejnerů, klikněte pravým tlačítkem na uzel řešení nebo projektu v **Průzkumníku řešení**a zvolte **Přidat > Podpora Orchestrace kontejnerů**. Klikněte na tlačítko **Docker Compose**, **Kubernetes a Helm**, nebo **Service Fabric** Spravovat kontejnery.

Když přidáte do projektu podporu Orchestrace kontejnerů, zobrazí se *soubor Dockerfile* přidány do projektu a **docker-compose** přidán do řešení ve složce **Průzkumníka řešení**, jak je znázorněno zde:

![Soubory docker v Průzkumníku řešení v sadě Visual Studio](media/visual-studio-tools-for-docker/docker-support-solution-explorer.png)

Pokud *docker-compose.yml* již existuje, požadovaných řádků kódu, konfigurace sady Visual Studio právě přidá k němu.

## <a name="configure-docker-tools"></a>Konfigurace nástroje Dockeru

V hlavní nabídce zvolte **nástroje > Možnosti**a rozbalte **nástroje kontejneru sady > Nastavení**. Nastavení nástroje kontejneru se zobrazí.

![Visual Studio Docker tools možnosti zobrazení: Automaticky získat požadované Image Dockeru při načtení projektu, automaticky spustit kontejnery na pozadí, automaticky ukončit kontejnery v řešení zavřít a nechcete zobrazovat výzvu pro důvěřující certifikát SSL.](./media/visual-studio-tools-for-docker/visual-studio-docker-tools-options.png)

V následující tabulce může pomoct při rozhodování, jak nastavit tyto možnosti.

| Name | Výchozí nastavení | Platí pro | Popis |
| -----|:---------------:|:----------:| ----------- |
| Automaticky získat požadované Image Dockeru při načtení projektu | On | Docker Compose | Pro zvýšení výkonu při načítání projektů sady Visual Studio spustí operaci Docker pull na pozadí tak, že až budete připraveni ke spuštění kódu, se image nestáhne již nebo probíhá stahování. Pokud jste právě načítá projekty a procházení kódu, můžete to vypnout aby se zabránilo stahování imagí kontejnerů, které nepotřebujete. |
| Automaticky spustit kontejnery na pozadí | On | Docker Compose | Znovu pro zajištění zvýšeného výkonu sady Visual Studio vytvoří kontejner s připojí svazek připravené pro když sestavíte a spustíte svůj kontejner. Pokud chcete řídit, kdy se vytvoří kontejner, vypněte toto. |
| Automaticky ukončit kontejnery na řešení zavřít | On | Docker Compose | Pokud byste o ni kontejnerů pro vaše řešení, aby kontinuálně běžely po zavření řešení nebo zavření sady Visual Studio, vypnutí této funkce. |
| Nezobrazovat výzvu důvěřující certifikátu SSL pro localhost | Off | Projekty ASP.NET Core 2.1 | Pokud localhost certifikát SSL není důvěryhodný, Visual Studio zobrazí výzvu pokaždé, když spuštění projektu, pokud je toto políčko zaškrtnuté. |

> [!WARNING]
> Pokud localhost certifikát SSL není důvěryhodný a zaškrtněte políčko pro potlačení výzvy k potvrzení, nemusí podařit HTTPS webové požadavky v době běhu ve vaší aplikaci nebo službě. V takovém případě zrušte zaškrtnutí políčka **nechcete zobrazovat výzvu** zaškrtávací políčko, spouštění vašeho projektu a označuje vztah důvěryhodnosti na řádku.

## <a name="next-steps"></a>Další kroky

Další podrobnosti o službách implementaci a použití sady Visual Studio tools pro práci s kontejnery, v následujících článcích:

[Ladění aplikací v místním kontejneru Dockeru](vs-azure-tools-docker-edit-and-refresh.md)

[Nasazení kontejneru ASP.NET do služby container registry pomocí sady Visual Studio](vs-azure-tools-docker-hosting-web-apps-in-docker.md)
