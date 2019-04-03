---
title: Visual Studio Tools for Docker s ASP.NET Core
author: ghogen
description: Naučte se používat nástroje Visual Studio 2019 a Docker pro Windows
ms.author: ghogen
ms.date: 02/01/2019
ms.prod: visual-studio-dev16
ms.technology: vs-azure
ms.topic: include
ms.openlocfilehash: 0fb367256f818e4bfd6e73a226c9eea1edb8a6b6
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/02/2019
ms.locfileid: "58872938"
---
Pomocí sady Visual Studio můžete snadno vytvářet, ladit a spouštění kontejnerizovaných aplikací ASP.NET Core a publikujte je na Azure Container Registry (ACR), Docker Hub, Azure App Service nebo vlastního registru kontejneru. V tomto článku budeme publikovat do služby ACR.

## <a name="prerequisites"></a>Požadavky

* [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) s **vývoj pro Web**, **nástroje Azure** úlohy, a/nebo **vývoj pro různé platformy .NET Core** nainstalovaná úloha
* [Aktualizace 2.2 vývojové nástroje .NET core](https://dotnet.microsoft.com/download/dotnet-core/2.2) pro vývoj aplikací pomocí .NET Core 2.2
* Chcete-li publikovat do služby Azure Container Registry, předplatné Azure. [Zaregistrujte si bezplatnou zkušební verzi](https://azure.microsoft.com/en-us/offers/ms-azr-0044p/).

## <a name="installation-and-setup"></a>Instalace a nastavení

Pro instalaci Dockeru, nejprve zkontrolujte informace na [Desktop Docker pro Windows: Co potřebujete vědět před instalací](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install). Dále nainstalujte [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows).

## <a name="add-a-project-to-a-docker-container"></a>Přidat projekt do kontejneru Dockeru

1. Vytvořte nový projekt pomocí **webové aplikace ASP.NET Core** šablony.
1. Vyberte **webovou aplikaci**a ujistěte se, že **povolit podporu Dockeru** zaškrtávací políčko zaškrtnuto.

   ![Povolit podporu Dockeru zaškrtávací políčko](../../media/docker-tools/vs-2019/create-new-web-application.PNG)

1. Vyberte typ kontejneru (Windows nebo Linux) a klikněte na **vytvořit**.

## <a name="dockerfile-overview"></a>Přehled souboru Dockerfile

A *soubor Dockerfile*, předpisu pro vytvoření finální image Dockeru, je vytvořen v projektu. Odkazovat na [odkaz na soubor Dockerfile](https://docs.docker.com/engine/reference/builder/) pro příkazy v rámci jeho pochopení.:

```
FROM microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM microsoft/dotnet:2.2-sdk-stretch AS build
WORKDIR /src
COPY ["HelloDockerTools/HelloDockerTools.csproj", "HelloDockerTools/"]
RUN dotnet restore "HelloDockerTools/HelloDockerTools.csproj"
COPY . .
WORKDIR "/src/HelloDockerTools"
RUN dotnet build "HelloDockerTools.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "HelloDockerTools.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "HelloDockerTools.dll"]
```

Předchozí *soubor Dockerfile* vychází [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) obrázků a obsahuje pokyny pro úpravu základní image tak, že sestavení vašeho projektu a jeho přidání do tohoto kontejneru.

Při nové dialogu projekt **konfigurace pro protokol HTTPS** zaškrtávací políčko zaškrtnuto, *soubor Dockerfile* poskytuje dva porty. Jeden port se používá pro přenos HTTP; jiný port se používá pro protokol HTTPS. Pokud políčko není zaškrtnuto, jeden port (80) je přístupný pro přenosy pomocí protokolu HTTP.

## <a name="debug"></a>Ladit

Vyberte **Docker** z ladění rozevírací seznam v panelu nástrojů a spusťte ladění aplikace. Může se zobrazit zpráva s výzvou o důvěřovat certifikátu; rozhodnete důvěřovat certifikátům, abyste mohli pokračovat.

**Kontejnerových nástrojů** možnost **výstup** okno zobrazuje, jaké akce probíhá.

Otevřít **Konzola správce balíčků** (PMC) v nabídce **nástroje**> Správce balíčků NuGet, **Konzola správce balíčků**.

Výsledný image Dockeru aplikace je označený jako *dev*. Na obrázku je založen na *2.2-aspnetcore-runtime* značku *microsoft/dotnet* základní image. Spustit `docker images` v příkaz **Konzola správce balíčků** okno (PMC). Image na počítači se zobrazí:

```console
REPOSITORY        TAG                     IMAGE ID      CREATED         SIZE
hellodockertools  dev                     d72ce0f1dfe7  30 seconds ago  255MB
microsoft/dotnet  2.2-aspnetcore-runtime  fcc3887985bb  6 days ago      255MB
```

> [!NOTE]
> **Dev** image neobsahuje binární soubory aplikace a další obsah, jako **ladění** konfigurace použít k poskytnutí iterace editace a ladění prostředí připojení svazku. Chcete-li vytvořit bitovou kopii produkčního prostředí obsahující veškerý obsah, použijte **vydání** konfigurace.

Spustit `docker ps` příkazu v konzole PMC. Všimněte si, že je aplikace spuštěna pomocí kontejneru:

```console
CONTAINER ID        IMAGE                  COMMAND               CREATED             STATUS              PORTS                                           NAMES
cf5d2ef5f19a        hellodockertools:dev   "tail -f /dev/null"   2 minutes ago       Up 2 minutes        0.0.0.0:52036->80/tcp, 0.0.0.0:44342->443/tcp   priceless_cartwright
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
    | **[Skladová jednotka (SKU)](https://docs.microsoft.com/azure/container-registry/container-registry-skus)** | Standard | Úrovně služby do registru kontejneru  |
    | **Umístění registru** | Vám nejbližším místě | Zvolte umístění, do [oblasti](https://azure.microsoft.com/regions/) vaší blízkosti nebo v blízkosti jiných služeb, které budou používat službu container registry. |

    ![Visual Studio vytvořit dialogové okno Azure Container Registry][0]

1. Klikněte na **Vytvořit**.

   ![Snímek obrazovky znázorňující úspěšné publikování](../../media/docker-tools/publish-succeeded.png)

## <a name="next-steps"></a>Další kroky

Můžete nyní využít kontejneru z registru na každém hostiteli podporuje spuštění imagí Dockeru, například [Azure Container Instances](/azure/container-instances/container-instances-tutorial-deploy-app).

## <a name="additional-resources"></a>Další zdroje

* [Kontejner vývoj pomocí sady Visual Studio](/visualstudio/containers)
* [Řešení potíží při vývoji v sadě Visual Studio 2017 pomocí Dockeru](../../vs-azure-tools-docker-troubleshooting-docker-errors.md)
* [Visual Studio Tools pro úložiště GitHub Dockeru](https://github.com/Microsoft/DockerTools)

[0]:../../media/vs-azure-tools-docker-hosting-web-apps-in-docker/vs-acr-provisioning-dialog-2019.png
