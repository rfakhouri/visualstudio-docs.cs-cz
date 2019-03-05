---
title: Ladění aplikací v místním kontejneru Dockeru | Dokumentace Microsoftu
description: Zjistěte, jak upravit aplikaci, která běží v místním kontejneru Dockeru, aktualizujte kontejneru prostřednictvím operace Edit and aktualizace a nastavení ladění zarážky
services: container-service
author: ghogen
manager: jillfra
ms.assetid: 480e3062-aae7-48ef-9701-e4f9ea041382
ms.topic: conceptual
ms.workload: multiple
ms.date: 03/01/2019
ms.author: ghogen
ms.openlocfilehash: 7f80681d4aa307675f73eac24d0fbe17c7c7b9a9
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/04/2019
ms.locfileid: "57323767"
---
# <a name="debugging-apps-in-a-local-docker-container"></a>Ladění aplikací v místním kontejneru Dockeru

## <a name="overview"></a>Přehled

Visual Studio 2017 poskytuje konzistentní způsob, jak vyvíjet v kontejneru Dockeru a ověřit vaše aplikace v místním prostředí.
Není nutné restartovat kontejneru pokaždé, když provedete změně kódu.
Tento článek ukazuje, jak použít funkci "Upravit a aktualizovat" ke spuštění základní webové aplikace v ASP.NET v místním kontejneru Dockeru, proveďte potřebné změny a pak aktualizujte prohlížeč, aby se tyto změny.
Tento článek také ukazuje, jak nastavit zarážky pro ladění.

## <a name="prerequisites"></a>Požadavky

Musí být nainstalované následující nástroje.

::: moniker range="vs-2017"

* [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) s nainstalovaná úloha vývoj pro Web.

::: moniker-end

::: moniker range="vs-2019"

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+rc) s nainstalovaná úloha vývoj pro Web.

::: moniker-end

Pro spouštění kontejnerů Docker místně, musíte klienta místní docker.
Můžete použít [nástrojů Dockeru](https://www.docker.com/products/docker-toolbox), což vyžaduje Hyper-V se deaktivuje, nebo můžete použít [Docker pro Windows](https://www.docker.com/get-docker), které používá technologie Hyper-V a vyžaduje Windows 10.

Pokud pomocí nástrojů Dockeru, budete muset [konfigurace klienta Dockeru](vs-azure-tools-docker-setup.md)

## <a name="1-create-a-web-app"></a>1. Vytvoření webové aplikace

[!INCLUDE [create-aspnet5-app](../azure/includes/create-aspnet5-app.md)]

## <a name="2-edit-your-code-and-refresh"></a>2. Upravit kód a aktualizace

Pokud chcete rychle iterovat změny, můžete spustit aplikaci v rámci kontejneru a pokračovat v provádění změn, zobrazení je jako při použití služby IIS Express.

1. Nastavte konfiguraci řešení na `Debug` a stiskněte klávesu  **&lt;CTRL + F5 >** k sestavení image dockeru a spouštět místně.

    Jakmile se image kontejneru je sestavený Build a běží v kontejneru Dockeru, spustí aplikace Visual Studio webové aplikace ve vašem výchozím prohlížeči.
    Pokud používáte prohlížeč Microsoft Edge nebo jinak obsahuje chyby, přečtěte si téma [Poradce při potížích s](vs-azure-tools-docker-troubleshooting-docker-errors.md) oddílu.
2. Přejděte na stránku o, což je, kde budeme provádět změny.
3. Vraťte se do sady Visual Studio a otevřete `Views\Home\About.cshtml`.
4. Na konec souboru přidejte následující obsah HTML a uložte změny.

    ```html
    <h1>Hello from a Docker Container!</h1>
    ```

5. Okno výstup, sledovat, i když se dokončí sestavení .NET a uvidíte tyto řádky, přepněte zpět do prohlížeče a aktualizujte stránku o.

   ```output
   Now listening on: http://*:80
   Application started. Press Ctrl+C to shut down
   ```

6. Vaše změny se použily!

## <a name="3-debug-with-breakpoints"></a>3. Ladění se zarážkami

Často změny potřebovat další kontroly, využívá funkce ladění sady Visual Studio.

1. Vraťte se do sady Visual Studio a otevřete `About.cshtml.cs`
2. Nahraďte obsah `OnGet` metoda následujícím kódem:

   ```cs
       Message = "Your application description page from within a Container";
   ```

3. Nastavte zarážku vlevo od řádku kódu.
4. Stisknutím klávesy F5 spusťte ladění.
5. Přejděte na stránku o narazila na zarážku.
6. Přepněte do sady Visual Studio zobrazíte zarážky a zkontrolovat hodnoty zprávy.

   ![Zarážky](media/vs-azure-tools-docker-edit-and-refresh/breakpoint.png)

## <a name="summary"></a>Souhrn

Podpora pro Docker v sadě Visual Studio 2017 umožňuje získat produktivitu místně, pracovat s produkční realitu vývoje v kontejneru Dockeru.

## <a name="troubleshooting"></a>Poradce při potížích

[Řešení potíží s vývojem Docker sady Visual Studio](vs-azure-tools-docker-troubleshooting-docker-errors.md)

## <a name="more-about-docker-with-visual-studio-windows-and-azure"></a>Další informace o Dockeru pomocí sady Visual Studio, Windows a Azure

* [Kontejner vývoj pomocí sady Visual Studio](/visualstudio/containers) – stránka centra vývoje kontejneru
* [Integrace dockeru pro Azure kanály](https://aka.ms/dockertoolsforvsts) – sestavování a nasazování kontejnerů dockeru
* [Nástroje dockeru pro Visual Studio Code](https://aka.ms/dockertoolsforvscode) – jazykové služby pro úpravy souborů dockeru ve více scénářích e2e už
* [Informace o kontejneru Windows](https://aka.ms/containers)– informace o Windows serveru a Nano Server
* [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/) - [dokumentace ke službě Azure Kubernetes Service](/azure/aks)
