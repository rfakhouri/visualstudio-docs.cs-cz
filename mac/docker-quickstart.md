---
title: Začínáme s Dockerem v sadě Visual Studio pro Mac
description: Zjistěte, jak přidat Dockeru do vašich projektů v sadě Visual Studio pro Mac
author: bytesguy
ms.author: adhartle
ms.date: 06/17/2019
ms.openlocfilehash: 8760bd048e23675c72fb7635587ca1c522b14259
ms.sourcegitcommit: fd5a5b057df3d733f5224c305096907989811f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/18/2019
ms.locfileid: "67196411"
---
# <a name="get-started-with-docker-in-visual-studio-for-mac"></a>Začínáme s Dockerem v sadě Visual Studio pro Mac

Pomocí sady Visual Studio pro Mac můžete snadno vytvářet, ladit a spouštět kontejnerizované ASP.NET Core aplikace a publikovat do Azure.

## <a name="prerequisites"></a>Požadavky

* [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-mac)
* [Visual Studio for Mac 2019](https://visualstudio.microsoft.com/vs/mac)

## <a name="installation-and-setup"></a>Instalace a nastavení

Pro instalaci Dockeru, přečtěte si a postupujte podle informací uvedených v [nainstalovat Docker Desktop pro Mac](https://docs.docker.com/docker-for-mac/install/).

## <a name="creating-an-aspnet-core-web-application-and-adding-docker-support"></a>Vytvoření webové aplikace ASP.NET Core a přidání podpory Dockeru

1. Vytvořit nové řešení tak, že přejdete do **soubor > Nový řešení**.
1. V části **.NET Core > aplikace** zvolte **webovou aplikaci** šablony: ![Vytvoření nové aplikace ASP.NET](media/docker-quickstart-1.png)
1. Vyberte cílovou architekturu. V tomto příkladu budeme používat .NET Core 2.2: ![Nastavení cílové architektury](media/docker-quickstart-2.png)
1. Zadejte podrobnosti o projektu, jako je například název (_DockerDemo_ v tomto příkladu). Vytvořený projekt obsahuje všechny základní informace, které potřebujete k sestavení a spuštění webu technologie ASP.NET Core.
1. V oblasti řešení klikněte pravým tlačítkem na projekt DockerDemo a vyberte **Add > Add Docker Support**: ![Přidání podpory dockeru](media/docker-quickstart-3.png)

Visual Studio pro Mac automaticky přidá nový projekt do řešení volá **docker-compose** a přidejte **soubor Dockerfile** do existujícího projektu.

![Podpůrné soubory generované dockeru](media/docker-quickstart-4.png)

## <a name="dockerfile-overview"></a>Přehled souboru Dockerfile

Soubor Dockerfile je předpisu pro vytvoření finální image Dockeru. Odkazovat na [odkaz na soubor Dockerfile](https://docs.docker.com/engine/reference/builder/) pro pochopení příkazy v rámci něj.

```
FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.2-sdk AS build
WORKDIR /src
COPY DockerDemo/DockerDemo.csproj DockerDemo/
RUN dotnet restore DockerDemo/DockerDemo.csproj
COPY . .
WORKDIR /src/DockerDemo
RUN dotnet build DockerDemo.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish DockerDemo.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "DockerDemo.dll"]
```

Předchozí *soubor Dockerfile* vychází [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) obrázků a obsahuje pokyny pro úpravu základní image tak, že sestavení vašeho projektu a jeho přidání do tohoto kontejneru.

> [!NOTE]
> Výchozí soubor Dockerfile vytvořených pomocí Visual Studia pro Mac zpřístupňuje Port 80 pro přenosy pomocí protokolu HTTP. Pokud chcete povolit provoz protokolu HTTPS, přidejte `Expose 443` k souboru Dockerfile.

## <a name="debugging"></a>Ladění

Vyberte `docker-compose` projekt jako spouštěný projekt a spustit ladění (**spuštění > Spustit ladění**). To bude vytvořit, nasadit a spustit projekt ASP.NET v kontejneru.

> [!TIP]
> Při prvním spuštění po instalaci Dockeru Desktop můžete obdržet následující chybu při pokusu o ladění: `Cannot start service dockerdemo: Mounts denied`
> 
> Přidat `/usr/local/share/dotnet/sdk/NuGetFallbackFolder` na kartě Sdílení souborů v Desktopu Dockeru:
>
> ![Přidání složky NuGetFallbackFolder do sdílení souborů](media/docker-quickstart-5.png)

Když se dokončí sestavení, spustí se aplikace v prohlížeči Safari:

![Výchozí projekt Dockeru, které jsou spuštěné v Safari](media/docker-quickstart-6.png)

Všimněte si, že kontejner bude naslouchat na portu, `http://localhost:32768` pro příklad a tento port se mohou lišit.

Pokud chcete zobrazit seznam spuštěných kontejnerů, použijte `docker ps` příkazu v terminálu.

Poznámka: přenosový port v následujícím snímku obrazovky (v části **porty**). Ukazuje to, že kontejner naslouchá na portu, které jsme viděli v Safari výše a předávání požadavků na interní webový server na portu 80 (jak jsou definovány v souboru Dockerfile). Z pohledu aplikace naslouchá na portu 80:

![Seznam kontejnerů dockeru](media/docker-quickstart-7.png)
