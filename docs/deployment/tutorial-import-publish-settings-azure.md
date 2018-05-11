---
title: Publikování v Azure pomocí importu nastavení publikování
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to Azure App Service
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
ms.openlocfilehash: a0fcc9f6ec4143a757139a9e013f1a1f4dbe666e
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>Publikování aplikace do služby Azure App Service pomocí importu nastavení publikování v sadě Visual Studio

Můžete použít **publikovat** nástroj k importu nastavení publikování a pak nasadíte aplikaci. V tomto článku používáme nastavení publikování pro služby Azure App Service, ale můžete podobný postup při importu nastavení publikování z [IIS](../deployment/tutorial-import-publish-settings-iis.md). V některých scénářích použití publikování, který profil nastavení může být rychlejší než ruční konfigurace nasazení se službou pro každou instalaci sady Visual Studio.

Tento postup platí pro aplikace ASP.NET, .NET Core a ASP.NET Core v sadě Visual Studio. Kroky odpovídají Visual Studio 2017 verze 15,6 operací.

V tomto kurzu provedete následující:

> [!div class="checklist"]
> * Generovat soubor nastavení publikování z Azure App Service
> * Importovat soubor nastavení publikování do sady Visual Studio
> * Nasazení aplikace do Azure App Service

Soubor nastavení publikování (*.publishsettings) je jiný než profil publikování (*.pubxml) vytvořit v sadě Visual Studio. Soubor nastavení publikování se vytvoří ve službě Azure App Service, a poté mohou být naimportovány do sady Visual Studio.

> [!NOTE]
> Pokud potřebujete jenom Kopírovat sady Visual Studio publikování profilu (\*.pubxml souboru) z jedné instalace sady Visual Studio na jiný, můžete najít profil publikování,  *\<profilename\>.pubxml*, v  *\\< název projektu\>\Properties\PublishProfiles* složku pro spravovaný projekt typy. Pro weby, podívejte se do části *\App_Data* složky. Publikování profily jsou soubory nástroje MSBuild XML.

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalovanou sadu Visual Studio a **ASP.NET** a **rozhraní .NET Framework** vývoj zatížení. Pro aplikace .NET Core, musíte taky **.NET Core** zatížení.

    Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).

* Vytvoření služby Azure App Service. Podrobné pokyny najdete v tématu [nasazení webové aplikace ASP.NET Core do Azure pomocí sady Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). 

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Vytvořte nový projekt ASP.NET v sadě Visual Studio

1. V počítači s Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně vyberte buď **webové aplikace ASP.NET (rozhraní .NET Framework)** nebo (C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na **OK**.

    Pokud nevidíte šablony zadaného projektu, klikněte **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Viz požadavky v tomto článku k identifikaci požadované sadě Visual Studio úloh, které je nutné nainstalovat.

1. Vyberte buď **MVC** (rozhraní .NET Framework) nebo **webové aplikace (Model-View-Controller)** (pro .NET Core) a ujistěte se, že **bez ověřování** je vybrána a potom klikněte na **OK**.

1. Zadejte název jako **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení > Sestavit řešení** a tím projekt sestavit.

## <a name="create-the-publish-settings-file-in-azure-app-service"></a>Vytvořte soubor nastavení publikování v Azure App Service

1. Na portálu Azure otevřete Azure App Service.

1. Klikněte na tlačítko **profilu publikování Get** profil místně a uložte ho.

    ![Získat profil publikování](../deployment/media/tutorial-azure-app-service-get-publish-profile.png)

    Soubor s *.publishsettings* přípona souboru byla vygenerována v umístění, kam jste jej uložili. Následující kód ukazuje částečné příklad souboru (v přehlednějším formátování).

    ```xml
    <publishData>
      <publishProfile
        profileName="DeployASPDotNetCore - Web Deploy"
        publishMethod="MSDeploy"
        publishUrl="deployaspdotnetcore.scm.azurewebsites.net:443"
        msdeploySite="DeployASPDotNetCore"
        userName="$DeployASPDotNetCore"
        userPWD="abcdefghijklmnopqrstuzwxyz"
        destinationAppUrl="http://deployaspdotnetcore20180508031824.azurewebsites.net"
        SQLServerDBConnectionString=""
        mySQLDBConnectionString=""
        hostingProviderForumLink=""
        controlPanelLink="http://windows.azure.com"
        webSystem="WebSites">
        <databases />
      </publishProfile>
    </publishData>
    ```
    Obvykle předchozí *.publishsettings soubor obsahuje dva profily publikování, které můžete použít v sadě Visual Studio, jeden pro nasazení pomocí nástroje nasazení webu a jeden pro nasazení pomocí protokolu FTP. Předchozí kód zobrazí profil nasazení webu. Oba profily se naimportují později při importu profil.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Import nastavení publikování v sadě Visual Studio a nasazení

1. V počítači, kde máte projekt ASP.NET, otevřete v sadě Visual Studio, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **publikovat**.

1. Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Klikněte na tlačítko **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogové okno, klikněte na tlačítko **importovat profil**.

    ![Zvolte publikování](../deployment/media/tutorial-publish-tool-import-profile.png)

1. Přejděte do umístění souboru nastavení publikování, který jste vytvořili v předchozí části.

1. V **soubor nastavení publikování importu** dialogové okno, vyberte profil, který jste vytvořili v předchozí části a klikněte na tlačítko **otevřete**.

1. Vyberte jednu ze dvou importované profily a klikněte na tlačítko **publikovat**.

    Sada Visual Studio spustí proces nasazení a ve výstupním okně zobrazuje průběh a výsledky.

## <a name="next-steps"></a>Další kroky

V tomto kurzu vytvořili soubor nastavení publikování, importovat do sady Visual Studio a nasazení aplikace ASP.NET do služby Azure App Service.

> [!div class="nextstepaction"]
> [První seznámení s nasazováním](../deployment/deploying-applications-services-and-components.md)
