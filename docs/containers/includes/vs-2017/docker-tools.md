---
title: Visual Studio Tools for Docker s ASP.NET Core
author: ghogen
description: Naučte se používat nástroje Visual Studio 2017 a Docker pro Windows
ms.author: ghogen
ms.date: 02/01/2019
ms.technology: vs-azure
ms.topic: include
ms.openlocfilehash: d4f29056d81ab926318b987c7197a37989af8b49
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55957644"
---
Pomocí sady Visual Studio můžete snadno vytvářet, ladit a spouštění kontejnerizovaných aplikací ASP.NET Core a publikujte je na Azure Container Registry (ACR), Docker Hub, Azure App Service nebo vlastního registru kontejneru. V tomto článku budeme publikovat do služby ACR.

## <a name="prerequisites"></a>Požadavky

* [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2017](https://visualstudio.microsoft.com/) s **vývoj pro Web**, **nástroje Azure** úlohy, a/nebo **vývoj pro různé platformy .NET Core** nainstalovaná úloha
* Chcete-li publikovat do služby Azure Container Registry, předplatné Azure. [Zaregistrujte si bezplatnou zkušební verzi](https://azure.microsoft.com/en-us/offers/ms-azr-0044p/).

## <a name="installation-and-setup"></a>Instalace a nastavení

Pro instalaci Dockeru, nejprve zkontrolujte informace na [Desktop Docker pro Windows: Co potřebujete vědět před instalací](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install). Dále nainstalujte [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows).

## <a name="add-a-project-to-a-docker-container"></a>Přidat projekt do kontejneru Dockeru

1. V nabídce sady Visual Studio vyberte **soubor > Nový > projekt**.
1. V části **šablony** část **nový projekt** dialogu **Visual C# > Web**.
1. Vyberte **webová aplikace ASP.NET Core**.
1. Pojmenujte novou aplikaci (nebo přijmout výchozí nastavení) a vyberte **OK**.
1. Vyberte **webovou aplikaci**.
1. Zkontrolujte, **povolit podporu Dockeru** zaškrtávací políčko.

   ![Povolit podporu Dockeru zaškrtávací políčko](../../media/docker-tools/enable-docker-support.PNG)

1. Vyberte typ kontejneru (Windows nebo Linux) a klikněte na **OK**.

## <a name="dockerfile-overview"></a>Přehled souboru Dockerfile

A *soubor Dockerfile*, předpisu pro vytvoření finální image Dockeru, je vytvořen v projektu. Odkazovat na [odkaz na soubor Dockerfile](https://docs.docker.com/engine/reference/builder/) pro příkazy v rámci jeho pochopení.:

```
FROM microsoft/dotnet:2.1-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 59518
EXPOSE 44364

FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /src
COPY HelloDockerTools/HelloDockerTools.csproj HelloDockerTools/
RUN dotnet restore HelloDockerTools/HelloDockerTools.csproj
COPY . .
WORKDIR /src/HelloDockerTools
RUN dotnet build HelloDockerTools.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish HelloDockerTools.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "HelloDockerTools.dll"]
```

Předchozí *soubor Dockerfile* vychází [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) obrázků a obsahuje pokyny pro úpravu základní image tak, že sestavení vašeho projektu a jeho přidání do tohoto kontejneru. 

Při nové dialogu projekt **konfigurace pro protokol HTTPS** zaškrtávací políčko zaškrtnuto, *soubor Dockerfile* poskytuje dva porty. Jeden port se používá pro přenos HTTP; jiný port se používá pro protokol HTTPS. Pokud políčko není zaškrtnuto, jeden port (80) je přístupný pro přenosy pomocí protokolu HTTP.

## <a name="debug"></a>Ladit

Vyberte **Docker** z ladění rozevírací seznam v panelu nástrojů a spusťte ladění aplikace. Může se zobrazit zpráva s výzvou o důvěřovat certifikátu; rozhodnete důvěřovat certifikátům, abyste mohli pokračovat.

**Výstup** okno zobrazuje, jaké akce probíhá.

Otevřít **Konzola správce balíčků** (PMC) v nabídce **nástroje**> Správce balíčků NuGet, **Konzola správce balíčků**.

Výsledný image Dockeru aplikace je označený jako *dev*. Na obrázku je založen na *modulu runtime 2.1 aspnetcore* značku *microsoft/dotnet* základní image. Spustit `docker images` v příkaz **Konzola správce balíčků** okno (PMC). Image na počítači se zobrazí:

```console
REPOSITORY        TAG                     IMAGE ID      CREATED         SIZE
hellodockertools  dev                     d72ce0f1dfe7  30 seconds ago  255MB
microsoft/dotnet  2.1-aspnetcore-runtime  fcc3887985bb  6 days ago      255MB
```

> [!NOTE]
> **Dev** image neobsahuje binární soubory aplikace a další obsah, jako **ladění** konfigurace použít k poskytnutí iterace editace a ladění prostředí připojení svazku. Chcete-li vytvořit bitovou kopii produkčního prostředí obsahující veškerý obsah, použijte **vydání** konfigurace.

Spustit `docker ps` příkazu v konzole PMC. Všimněte si, že je aplikace spuštěna pomocí kontejneru:

```console
CONTAINER ID        IMAGE                  COMMAND                   CREATED             STATUS              PORTS                   NAMES
baf9a678c88d        hellodockertools:dev   "C:\\remote_debugge..."   21 seconds ago      Up 19 seconds       0.0.0.0:37630->80/tcp   dockercompose4642749010770307127_hellodockertools_1
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

1. Klikněte na **Vytvořit**.

## <a name="next-steps"></a>Další kroky

Můžete nyní využít kontejneru z registru na každém hostiteli podporuje spuštění imagí Dockeru, například [Azure Container Instances](/azure/container-instances/container-instances-tutorial-deploy-app).

## <a name="additional-resources"></a>Další zdroje

* [Kontejner vývoj pomocí sady Visual Studio](/visualstudio/containers)
* [Řešení potíží s Visual Studio 2017 vývoj aplikací pomocí Dockeru](../../vs-azure-tools-docker-troubleshooting-docker-errors.md)
* [Visual Studio Tools pro úložiště GitHub Dockeru](https://github.com/Microsoft/DockerTools)

[0]:../../media/vs-azure-tools-docker-hosting-web-apps-in-docker/vs-acr-provisioning-dialog.png
