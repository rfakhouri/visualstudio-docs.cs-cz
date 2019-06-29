---
title: Nástroje kontejneru sady Visual Studio pomocí ASP.NET Core
author: ghogen
description: Další informace o použití nástroje kontejneru sady Visual Studio a Docker pro Windows
ms.author: ghogen
ms.date: 06/06/2019
ms.technology: vs-azure
ms.topic: quickstart
ms.openlocfilehash: 09209393ea32b4eb9b86a8c0c4263103ee5de344
ms.sourcegitcommit: 0cd282a7584b9bfd4df7882f8fdf3ad8a270e219
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2019
ms.locfileid: "67465096"
---
# <a name="quickstart-use-docker-with-a-react-single-page-app-in-visual-studio"></a>Rychlý start: Použití Docker s React jednostránkovou aplikaci, a to v sadě Visual Studio

Pomocí sady Visual Studio, můžete snadno vytvářet, ladit a spouštění kontejnerizovaných ASP.NET Core aplikací, včetně těch s použitím jazyka JavaScript na straně klienta, jako je například React.js jednostránkové aplikace a publikovat je do Azure Container Registry (ACR), Docker Hub, Azure App Service, nebo vlastní registr kontejnerů. V tomto článku budeme publikovat do služby ACR.

## <a name="prerequisites"></a>Požadavky

::: moniker range="vs-2017"
* [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) s **vývoj pro Web**, **nástroje Azure** úlohy, a/nebo **vývoj pro různé platformy .NET Core** nainstalovaná úloha
* Chcete-li publikovat do služby Azure Container Registry, předplatné Azure. [Zaregistrujte si bezplatnou zkušební verzi](https://azure.microsoft.com/offers/ms-azr-0044p/).
::: moniker-end
::: moniker range=">=vs-2019"
* [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) s **vývoj pro Web**, **nástroje Azure** úlohy, a/nebo **vývoj pro různé platformy .NET Core** nainstalovaná úloha
* [Aktualizace 2.2 vývojové nástroje .NET core](https://dotnet.microsoft.com/download/dotnet-core/2.2) pro vývoj aplikací pomocí .NET Core 2.2
* Chcete-li publikovat do služby Azure Container Registry, předplatné Azure. [Zaregistrujte si bezplatnou zkušební verzi](https://azure.microsoft.com/offers/ms-azr-0044p/).
::: moniker-end

## <a name="installation-and-setup"></a>Instalace a nastavení

Pro instalaci Dockeru, nejprve zkontrolujte informace na [Desktop Docker pro Windows: Co potřebujete vědět před instalací](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install). Dále nainstalujte [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows).

## <a name="create-a-project-and-add-docker-support"></a>Vytvořte projekt a přidat podporu Dockeru

::: moniker range="vs-2017"
1. Vytvořte nový projekt pomocí **webové aplikace ASP.NET Core** šablony.
1. Vyberte **React.js**. Nelze vybrat **povolit podporu Dockeru**, ale Nedělejte si starosti, po vytvoření projektu můžete přidat, které podporují.

   ![Snímek obrazovky nového projektu React.js](media/container-tools-react/vs2017/new-react-project.png)

1. Klikněte pravým tlačítkem na uzel projektu a zvolte **přidat** > **podporu Dockeru** souboru Dockerfile přidat do projektu.

   ![Přidání podpory Dockeru](media/container-tools-react/vs2017/add-docker-support.png)

1. Vyberte typ kontejneru Linuxu a klikněte na tlačítko **OK**.
::: moniker-end
::: moniker range=">=vs-2019"
1. Vytvořte nový projekt pomocí **webové aplikace ASP.NET Core** šablony.
1. Vyberte **React.js**a klikněte na tlačítko **vytvořit**. Nelze vybrat **povolit podporu Dockeru**, ale Nedělejte si starosti, můžete přidat později, které podporují.

   ![Snímek obrazovky nového projektu React.js](media/container-tools-react/vs2019/new-react-project.png)

1. Klikněte pravým tlačítkem na uzel projektu a zvolte **přidat** > **podporu Dockeru** souboru Dockerfile přidat do projektu.

   ![Přidání podpory Dockeru](media/container-tools-react/vs2017/add-docker-support.png)

1. Vyberte jako typ kontejneru Linuxu.
::: moniker-end

## <a name="dockerfile-overview"></a>Přehled souboru Dockerfile

A *soubor Dockerfile*, předpisu pro vytvoření finální image Dockeru, je vytvořen v projektu. Odkazovat na [odkaz na soubor Dockerfile](https://docs.docker.com/engine/reference/builder/) pro pochopení příkazy v rámci něj.

Otevřít *soubor Dockerfile* v projektu a přidejte následující řádky a nainstalujte Node.js 10.x v kontejneru. Přidejte tyto řádky v první části, chcete-li přidat instalace Node package Manageru *npm.exe* na základní image, který se používá v dalších krocích.

```
RUN curl -sL https://deb.nodesource.com/setup_10.x |  bash -
RUN apt-get install -y nodejs
```

*Soubor Dockerfile* by teď měl vypadat přibližně takto:

```
FROM microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim AS base
WORKDIR /app
EXPOSE 80 
EXPOSE 443
RUN curl -sL https://deb.nodesource.com/setup_10.x |  bash -
RUN apt-get install -y nodejs

FROM microsoft/dotnet:2.2-sdk-stretch AS build
WORKDIR /src
COPY ["WebApplication37/WebApplication37.csproj", "WebApplication37/"]
RUN dotnet restore "WebApplication37/WebApplication37.csproj"
COPY . .
WORKDIR "/src/WebApplication37"
RUN dotnet build "WebApplication37.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication37.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication37.dll"]
```

Předchozí *soubor Dockerfile* vychází [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) obrázků a obsahuje pokyny pro úpravu základní image tak, že sestavení vašeho projektu a jeho přidání do tohoto kontejneru.

Při nové dialogu projekt **konfigurace pro protokol HTTPS** zaškrtávací políčko zaškrtnuto, *soubor Dockerfile* poskytuje dva porty. Jeden port se používá pro přenos HTTP; jiný port se používá pro protokol HTTPS. Pokud políčko není zaškrtnuto, jeden port (80) je přístupný pro přenosy pomocí protokolu HTTP.

## <a name="debug"></a>Ladění

Vyberte **Docker** z ladění rozevírací seznam v panelu nástrojů a spusťte ladění aplikace. Může se zobrazit zpráva s výzvou o důvěřovat certifikátu; rozhodnete důvěřovat certifikátům, abyste mohli pokračovat.

**Kontejnerových nástrojů** možnost **výstup** okno zobrazuje, jaké akce probíhá. Měli byste vidět instalační postup, který je přidružený k *npm.exe*.

Prohlížeč zobrazí domovská stránka vaší aplikace.

::: moniker range="vs-2017"
   ![Snímek obrazovky s aplikací](media/container-tools-react/vs2017/running-app.png)
::: moniker-end
::: moniker range=">=vs-2019"
   ![Snímek obrazovky s aplikací](media/container-tools-react/vs2019/running-app.png)
::: moniker-end

Zkuste přejít na stránku *čítač* stránce a testovat kód na straně klienta pro čítač kliknutím **přírůstek** tlačítko.

Otevřít **Konzola správce balíčků** (PMC) v nabídce **nástroje**> Správce balíčků NuGet, **Konzola správce balíčků**.

Výsledný image Dockeru aplikace je označený jako *dev*. Na obrázku je založen na *2.2-aspnetcore-runtime* značku *microsoft/dotnet* základní image. Spustit `docker images` v příkaz **Konzola správce balíčků** okno (PMC). Image na počítači se zobrazí:

```console
REPOSITORY        TAG                     IMAGE ID      CREATED         SIZE
webapplication37  dev                     d72ce0f1dfe7  30 seconds ago  255MB
microsoft/dotnet  2.2-aspnetcore-runtime  fcc3887985bb  6 days ago      255MB
```

> [!NOTE]
> **Dev** image neobsahuje binární soubory aplikace a další obsah, jako **ladění** konfigurace použít k poskytnutí iterace editace a ladění prostředí připojení svazku. Chcete-li vytvořit bitovou kopii produkčního prostředí obsahující veškerý obsah, použijte **vydání** konfigurace.

Spustit `docker ps` příkazu v konzole PMC. Všimněte si, že je aplikace spuštěna pomocí kontejneru:

```console
CONTAINER ID        IMAGE                  COMMAND               CREATED             STATUS              PORTS                                           NAMES
cf5d2ef5f19a        webapplication37:dev   "tail -f /dev/null"   2 minutes ago       Up 2 minutes        0.0.0.0:52036->80/tcp, 0.0.0.0:44342->443/tcp   priceless_cartwright
```

## <a name="publish-docker-images"></a>Publikování Image Dockeru

Po dokončení cyklu vývoje a ladění aplikace můžete vytvořit image produkční aplikace.

1. Změna konfigurace rozevíracího seznamu **vydání** a sestavení aplikace.
1. Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a zvolte **publikovat**.
1. V dialogovém okně Publikovat cíl, vyberte **Container Registry** kartu.
1. Zvolte **vytvořit nový registr kontejneru Azure** a klikněte na tlačítko **publikovat**.
1. Vyplňte požadované hodnoty v **vytvořit nový registr kontejneru Azure**.

    | Nastavení      | Navrhovaná hodnota  | Popis                                |
    | ------------ |  ------- | -------------------------------------------------- |
    | **DNS Prefix** | Globálně jedinečný název | Název, který jednoznačně identifikuje vašeho registru kontejneru. |
    | **Předplatné** | Vaše předplatné | Předplatné Azure používat. |
    | **[Skupina prostředků](/azure/azure-resource-manager/resource-group-overview)** | myResourceGroup |  Název skupiny prostředků, ve kterém chcete vytvořit registr kontejnerů. Zvolte **nový** vytvořit novou skupinu prostředků.|
    | **[SKLADOVÁ POLOŽKA](https://docs.microsoft.com/azure/container-registry/container-registry-skus)** | Standard | Úrovně služby do registru kontejneru  |
    | **Umístění registru** | Vám nejbližším místě | Zvolte umístění, do [oblasti](https://azure.microsoft.com/regions/) vaší blízkosti nebo v blízkosti jiných služeb, které budou používat službu container registry. |

    ![Visual Studio vytvořit dialogové okno Azure Container Registry][0]

1. Klikněte na možnost **Vytvořit**.

   ![Snímek obrazovky znázorňující úspěšné publikování](media/container-tools/publish-succeeded.png)

## <a name="next-steps"></a>Další kroky

Můžete nyní využít kontejneru z registru na každém hostiteli podporuje spuštění imagí Dockeru, například [Azure Container Instances](/azure/container-instances/container-instances-tutorial-deploy-app).

## <a name="additional-resources"></a>Další zdroje

* [Kontejner vývoj pomocí sady Visual Studio](/visualstudio/containers)
* [Řešení potíží s Visual Studio vývoj aplikací pomocí Dockeru](troubleshooting-docker-errors.md)
* [Úložiště Visual Studio kontejner nástroje Githubu](https://github.com/Microsoft/DockerTools)

::: moniker range="vs-2017"
[0]:media/hosting-web-apps-in-docker/vs-acr-provisioning-dialog.png
::: moniker-end
::: moniker range=">=vs-2019"
[0]:media/hosting-web-apps-in-docker/vs-acr-provisioning-dialog-2019.png
::: moniker-end