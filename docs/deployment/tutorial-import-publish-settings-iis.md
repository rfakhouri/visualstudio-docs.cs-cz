---
title: Publikování do služby IIS pomocí importu nastavení publikování
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to IIS
ms.date: 05/07/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02e6ae6e06daf43a6aec08097df2b37a21d2aaa3
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766669"
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>Publikování aplikace do služby IIS pomocí importu nastavení publikování v sadě Visual Studio

Můžete použít **publikovat** nástroj k importu nastavení publikování a pak nasadíte aplikaci. V tomto článku používáme nastavení publikování pro službu IIS, ale můžete podobný postup při importu nastavení publikování pro [Azure App Service](../deployment/tutorial-import-publish-settings-azure.md). V některých scénářích použití publikování, který profil nastavení může být rychlejší než ruční konfigurace nasazení pro službu IIS pro každou instalaci sady Visual Studio.

Tento postup platí pro aplikace ASP.NET, .NET Core a ASP.NET Core v sadě Visual Studio. Kroky odpovídají Visual Studio 2017 verze 15,6 operací.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Konfigurace služby IIS tak, aby může generovat soubor nastavení publikování
> * Vytvořte soubor nastavení publikování
> * Importovat soubor nastavení publikování do sady Visual Studio
> * Nasaďte aplikaci do služby IIS

Soubor nastavení publikování (*\*.publishsettings*) je jiný než profil publikování (*\*.pubxml*) vytvořit v sadě Visual Studio. Soubor nastavení publikování se vytvoří pomocí služby IIS nebo Azure App Service, nebo ji můžete ručně vytvořit a potom ji můžete importovat do sady Visual Studio.

> [!NOTE]
> Pokud potřebujete jenom Kopírovat sady Visual Studio publikování profilu (\*.pubxml souboru) z jedné instalace sady Visual Studio na jiný, můžete najít profil publikování,  *\<profilename\>.pubxml*, v  *\\< název projektu\>\Properties\PublishProfiles* složku pro spravovaný projekt typy. Pro weby, podívejte se do části *\App_Data* složky. Publikování profily jsou soubory nástroje MSBuild XML.

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalované Visual Studio 2017 a **ASP.NET** a **rozhraní .NET Framework** vývoj zatížení. Pro aplikace .NET Core, musíte taky **.NET Core** zatížení.

    Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

* Generovat soubor nastavení publikování ze služby IIS, musíte mít počítač se systémem Windows Server 2012 nebo Windows Server 2016 a musí mít roli Webový Server IIS správně nakonfigurovaný. Také musí být nainstalována technologie ASP.NET 4.5 nebo ASP.NET Core. ASP.NET Core, najdete v části [publikování do služby IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration). Technologie ASP.NET 4.5, najdete v části [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Vytvořte nový projekt ASP.NET v sadě Visual Studio

1. V počítači s Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně vyberte buď **webové aplikace ASP.NET (rozhraní .NET Framework)** nebo (C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na **OK**.

    Pokud nevidíte šablony zadaného projektu, klikněte **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí se instalační program pro Visual Studio. Viz požadavky v tomto článku k identifikaci požadované sadě Visual Studio úloh, které je nutné nainstalovat.

1. Vyberte buď **MVC** (rozhraní .NET Framework) nebo **webové aplikace (Model-View-Controller)** (pro .NET Core) a ujistěte se, že **bez ověřování** je vybrána a potom klikněte na **OK**.

1. Zadejte název jako **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení > Sestavit řešení** a tím projekt sestavit.

## <a name="install-and-configure-web-deploy-on-windows-server"></a>Instalace a konfigurace nasazení webu v systému Windows Server

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Vytvořte soubor nastavení publikování ve službě IIS v systému Windows Server

[!INCLUDE [create-publish-settings-iis](../deployment/includes/create-publish-settings-iis.md)]

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Import nastavení publikování v sadě Visual Studio a nasazení

[!INCLUDE [import-publish-settings](../deployment/includes/import-publish-settings-vs.md)]

Po aplikaci nasadí úspěšně, by se měl spustit automaticky. Pokud se nespustí ze sady Visual Studio, spusťte aplikaci ve službě IIS. Pro ASP.NET Core, musíte zajistit, že fond aplikací pole pro **DefaultAppPool** je nastaven na **bez spravovaného kódu**.

## <a name="next-steps"></a>Další kroky

V tomto kurzu vytvořili soubor nastavení publikování, importovat do sady Visual Studio a nasazení aplikace ASP.NET do služby IIS. Můžete chtít přehled další možnosti publikování v sadě Visual Studio.

> [!div class="nextstepaction"]
> [První seznámení s nasazováním](../deployment/deploying-applications-services-and-components.md)
