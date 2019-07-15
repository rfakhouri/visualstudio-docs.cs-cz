---
title: Ladění aplikací v místním kontejneru Dockeru | Dokumentace Microsoftu
description: Zjistěte, jak upravit aplikaci, která běží v místním kontejneru Dockeru, aktualizujte kontejneru prostřednictvím operace Edit and aktualizace a potom nastavte body přerušení ladění.
author: ghogen
manager: jillfra
ms.assetid: 480e3062-aae7-48ef-9701-e4f9ea041382
ms.topic: conceptual
ms.workload: multiple
ms.date: 03/05/2019
ms.author: ghogen
ms.technology: vs-azure
ms.openlocfilehash: d4ac06d07fd6e59ea8db2ead13c0dc493e36b282
ms.sourcegitcommit: 748d9cd7328a30f8c80ce42198a94a4b5e869f26
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67890671"
---
# <a name="debug-apps-in-a-local-docker-container"></a>Ladění aplikací v místním kontejneru Dockeru

Visual Studio poskytuje konzistentní způsob, jak vyvíjet v kontejneru Dockeru a ověřit vaše aplikace v místním prostředí. Není nutné restartovat kontejneru pokaždé, když provedete změně kódu.

Tento článek ukazuje, jak použít funkci upravit a aktualizovat v sadě Visual Studio ke spuštění webové aplikace ASP.NET Core v místním kontejneru Dockeru, provést změny a pak aktualizujte prohlížeč, aby se změny projevily. Tento článek také ukazuje, jak nastavit zarážky pro ladění.

## <a name="prerequisites"></a>Požadavky

Chcete-li ladit aplikace v místním kontejneru Dockeru, je nutné nainstalovat následující nástroje:

::: moniker range="vs-2017"

* [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) s nainstalovaná úloha vývoj pro Web

::: moniker-end

::: moniker range="vs-2019"

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) s nainstalovaná úloha vývoj pro Web

::: moniker-end

Pro spouštění kontejnerů Docker místně, musíte mít místního klienta Dockeru. Můžete použít [nástrojů Dockeru](https://www.docker.com/products/docker-toolbox), což vyžaduje Hyper-V se deaktivuje. Můžete také použít [Docker pro Windows](https://www.docker.com/get-docker), které používá technologie Hyper-V a vyžaduje Windows 10. Pokud používáte nástrojů Dockeru, musíte nakonfigurovat klienta Dockeru.

Kontejnery dockeru jsou k dispozici pro projekty .NET Framework a .NET Core. Pojďme se podívat na dva příklady. Nejprve podíváme na webovou aplikaci .NET Core. Potom podíváme na konzolovou aplikaci .NET Framework.

## <a name="create-a-web-app"></a>Vytvoření webové aplikace

::: moniker range="vs-2017"
[!INCLUDE [create-aspnet5-app](../azure/includes/create-aspnet5-app.md)]
::: moniker-end
::: moniker range=">= vs-2019"
[!INCLUDE [create-aspnet5-app-2019](../azure/includes/vs-2019/create-aspnet5-app-2019.md)
::: moniker-end

### <a name="edit-your-code-and-refresh"></a>Upravit kód a aktualizace

Pokud chcete rychle iterovat změny, můžete spustit aplikaci v kontejneru. Pak pokračujte v provádění změn, zobrazení je jako při použití služby IIS Express.

1. Nastavte **konfigurace řešení** k **ladění**. Stiskněte Ctrl + F5 sestavte image Dockeru a spusťte místně.

    Když vytvořené image kontejneru a spuštění v kontejneru Dockeru, Visual Studio spustí webovou aplikaci ve vašem výchozím prohlížeči.

2. Přejděte *Index* stránky. Uděláme změny na této stránce.
3. Vraťte se do sady Visual Studio a otevřete *Index.cshtml*.
4. Na konec souboru přidejte následující obsah HTML a následně změny uložte.

    ```html
    <h1>Hello from a Docker container!</h1>
    ```

5. V okně výstup po dokončení sestavení .NET a uvidíte následující řádky, přepněte zpět do prohlížeče a aktualizujte stránku:

   ```output
   Now listening on: http://*:80
   Application started. Press Ctrl+C to shut down.
   ```

Vaše změny se použily!

### <a name="debug-with-breakpoints"></a>Ladění se zarážkami

Často změny vyžadují další kontroly. Funkce ladění sady Visual Studio můžete použít pro tuto úlohu.

1. V sadě Visual Studio, otevřete *Index.cshtml.cs*.
2. Nahraďte obsah `OnGet` metodu s následujícím kódem:

   ```csharp
       ViewData["Message"] = "Your application description page from within a container";
   ```

3. Vlevo od řádku kódu nastavte zarážku.
4. Pokud chcete spustit ladění a zarážce, stiskněte klávesu F5.
5. Přepnout do sady Visual Studio zobrazíte zarážku. Zkontrolujte hodnoty.

   ![Zarážky](media/edit-and-refresh/breakpoint.png)

## <a name="create-a-net-framework-console-app"></a>Vytvoření konzolové aplikace .NET Framework

Při použití projekty aplikace konzoly rozhraní .NET Framework není podporována možnost přidat podporu Dockeru bez Orchestrace. Následující postup můžete použít i nadále i v případě, že používáte pouze jednoho projektu Dockeru.

1. Vytvoření nového projektu aplikace konzoly rozhraní .NET Framework.
1. V Průzkumníku řešení klikněte pravým tlačítkem myši na uzel projektu a pak vyberte **přidat** > **podpora Orchestrace kontejnerů**.  V dialogovém okně, které se zobrazí, vyberte **Docker Compose**. Soubor Dockerfile se přidá do vašeho projektu a je přidán projekt Docker Compose s přidružené podpůrné soubory.

### <a name="debug-with-breakpoints"></a>Ladění se zarážkami

1. V Průzkumníku řešení otevřete *Program.cs*.
2. Nahraďte obsah `Main` metodu s následujícím kódem:

   ```csharp
       System.Console.WriteLine("Hello, world!");
   ```

3. Nastavte zarážku vlevo od řádku kódu.
4. Stisknutím klávesy F5 spusťte ladění a zarážce.
5. Přepněte do aplikace Visual Studio zobrazit zarážky a zkontrolovat hodnoty.

   ![Zarážky](media/edit-and-refresh/breakpoint-console.png)

## <a name="container-reuse"></a>Opětovné použití kontejnerů

Během cyklu vývoje sady Visual Studio znovu sestaví pouze imagí kontejnerů a kontejner sám o sobě při změně souboru Dockerfile. Pokud nezměníte soubor Dockerfile, Visual Studio znovu použije kontejneru z předchozích spuštění.

Pokud jste ručně změnili kontejneru a chcete znovu s image kontejneru čisté, použijte **sestavení** > **Vyčistit** příkazů v sadě Visual Studio a následně vytvořit jako obvykle.

## <a name="troubleshoot"></a>Řešení potíží

Zjistěte, jak [řešení potíží s Visual Studio Docker vývoj](troubleshooting-docker-errors.md).

## <a name="more-about-docker-with-visual-studio-windows-and-azure"></a>Další informace o Dockeru pomocí sady Visual Studio, Windows a Azure

* Další informace o [kontejneru vývoj pomocí sady Visual Studio](/visualstudio/containers).
* K vytvoření a nasazení kontejneru Dockeru, naleznete v tématu [integrace Dockeru pro Azure kanály](https://aka.ms/dockertoolsforvsts).
* Rejstřík článků Windows Server a Nano Server, naleznete v tématu [informací o kontejneru Windows](https://aka.ms/containers).
* Další informace o [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/) a zkontrolujte [dokumentace ke službě Azure Kubernetes Service](/azure/aks).

