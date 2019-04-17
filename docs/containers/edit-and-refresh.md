---
title: Ladění aplikací v místním kontejneru Dockeru | Dokumentace Microsoftu
description: Zjistěte, jak upravit aplikaci, která běží v místním kontejneru Dockeru, aktualizujte kontejneru prostřednictvím operace Edit and aktualizace a nastavení ladění zarážky
author: ghogen
manager: jillfra
ms.assetid: 480e3062-aae7-48ef-9701-e4f9ea041382
ms.topic: conceptual
ms.workload: multiple
ms.date: 03/05/2019
ms.author: ghogen
ms.technology: vs-azure
ms.openlocfilehash: 5cc386ae0d9a9d19acf3590786773e9efbda2725
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59658035"
---
# <a name="debugging-apps-in-a-local-docker-container"></a>Ladění aplikací v místním kontejneru Dockeru

## <a name="overview"></a>Přehled

Visual Studio poskytuje konzistentní způsob, jak vyvíjet v kontejneru Dockeru a ověřit vaše aplikace v místním prostředí.
Není nutné restartovat kontejneru pokaždé, když provedete změně kódu.
Tento článek ukazuje, jak použít funkci "Upravit a aktualizovat" ke spuštění základní webové aplikace v ASP.NET v místním kontejneru Dockeru, proveďte potřebné změny a pak aktualizujte prohlížeč, aby se tyto změny.
Tento článek také ukazuje, jak nastavit zarážky pro ladění.

## <a name="prerequisites"></a>Požadavky

Musí být nainstalované následující nástroje.

::: moniker range="vs-2017"

* [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) s nainstalovaná úloha vývoj pro Web.

::: moniker-end

::: moniker range="vs-2019"

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) s nainstalovaná úloha vývoj pro Web.

::: moniker-end

Pro spouštění kontejnerů Docker místně, musíte klienta místní docker.
Můžete použít [nástrojů Dockeru](https://www.docker.com/products/docker-toolbox), což vyžaduje Hyper-V se deaktivuje, nebo můžete použít [Docker pro Windows](https://www.docker.com/get-docker), které používá technologie Hyper-V a vyžaduje Windows 10.

Pokud pomocí nástrojů Dockeru, musíte nakonfigurovat klienta Dockeru.

## <a name="1-create-a-web-app"></a>1. Vytvoření webové aplikace

::: moniker range="vs-2017"
[!INCLUDE [create-aspnet5-app](../azure/includes/create-aspnet5-app.md)]
::: moniker-end
::: moniker range=">= vs-2019"
[!INCLUDE [create-aspnet5-app-2019](../azure/includes/vs-2019/create-aspnet5-app-2019.md)
::: moniker-end

## <a name="2-edit-your-code-and-refresh"></a>2. Upravit kód a aktualizace

Pokud chcete rychle iterovat změny, můžete spustit aplikaci v rámci kontejneru a pokračovat v provádění změn, zobrazení je jako při použití služby IIS Express.

1. Nastavte konfiguraci řešení na `Debug` a stisknutím kláves Ctrl + F5 sestavte image dockeru a spusťte místně.

    Jakmile se image kontejneru je sestavený Build a běží v kontejneru Dockeru, Visual Studio spustí webovou aplikaci ve vašem výchozím prohlížeči.

2. Přejděte na stránku Index, který je, kde budeme provádět změny.
3. Vraťte se do sady Visual Studio a otevřete `Index.cshtml`.
4. Na konec souboru přidejte následující obsah HTML a uložte změny.

    ```html
    <h1>Hello from a Docker Container!</h1>
    ```

5. Okno výstup, sledovat, i když se dokončí sestavení .NET a uvidíte tyto řádky, přepněte zpět do prohlížeče a aktualizujte stránku.

   ```output
   Now listening on: http://*:80
   Application started. Press Ctrl+C to shut down
   ```

6. Vaše změny se použily!

## <a name="3-debug-with-breakpoints"></a>3. Ladění se zarážkami

Často změny potřebovat další kontroly, využívá funkce ladění sady Visual Studio.

1. Vraťte se do sady Visual Studio a otevřete `Index.cshtml.cs`
2. Nahraďte obsah `OnGet` metoda následujícím kódem:

   ```csharp
       ViewData["Message"] = "Your application description page from within a Container";
   ```

3. Nastavte zarážku vlevo od řádku kódu.
4. Stisknutím klávesy F5 spusťte ladění a zarážce.
5. Přepněte do aplikace Visual Studio zobrazit zarážky, kontrolovat hodnoty a tak dále.

   ![Zarážky](media/edit-and-refresh/breakpoint.png)

## <a name="summary"></a>Souhrn

S podporou Dockeru v sadě Visual Studio můžete získat produktivitu místně, pracovat s produkční realitu vývoje v kontejneru Dockeru.

## <a name="troubleshooting"></a>Poradce při potížích

[Řešení potíží s vývojem Docker sady Visual Studio](troubleshooting-docker-errors.md)

## <a name="more-about-docker-with-visual-studio-windows-and-azure"></a>Další informace o Dockeru pomocí sady Visual Studio, Windows a Azure

* [Kontejner vývoj pomocí sady Visual Studio](/visualstudio/containers) – vývoj kontejnerů, úvodní stránka
* [Integrace dockeru pro Azure kanály](https://aka.ms/dockertoolsforvsts) – sestavování a nasazování kontejnerů dockeru
* [Informace o kontejneru Windows](https://aka.ms/containers)– informace o Windows serveru a Nano Server
* [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/) - [dokumentace ke službě Azure Kubernetes Service](/azure/aks)
