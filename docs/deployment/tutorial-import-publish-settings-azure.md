---
title: Publikování do Azure pomocí importu nastavení publikování
description: Vytváření a import profilu publikování k nasazení aplikace v sadě Visual Studio do služby Azure App Service
ms.date: 05/07/2018
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bd040b613a5b982050d651f341456c5fafc2954b
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65679189"
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>Publikování aplikace do služby Azure App Service pomocí importu nastavení publikování v sadě Visual Studio

Můžete použít **publikovat** nástroj k importu nastavení publikování a pak nasadíte aplikaci. V tomto článku používáme nastavení publikování pro Azure App Service, ale můžete použít podobným způsobem k importu nastavení publikování z [IIS](../deployment/tutorial-import-publish-settings-iis.md). V některých scénářích použití publikování profilu nastavení může být rychlejší než ruční konfigurace nasazení do služby pro každou instalaci sady Visual Studio.

Tento postup platí pro aplikace ASP.NET, ASP.NET Core a .NET Core v sadě Visual Studio. Můžete také importovat nastavení publikování pro [Python](../python/publishing-python-web-applications-to-azure-from-visual-studio.md) aplikace.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Generovat soubor nastavení publikování z Azure App Service
> * Importovat soubor nastavení publikování do sady Visual Studio
> * Nasaďte aplikaci do služby Azure App Service

Soubor nastavení publikování (*\*.publishsettings*) se liší od profil publikování (*\*.pubxml*) vytvořené v sadě Visual Studio. Soubor nastavení publikování se vytvoří ve službě Azure App Service, a pak mohou být naimportovány do sady Visual Studio.

> [!NOTE]
> Pokud potřebujete jenom zkopírujte sady Visual Studio profil publikování (*\*.pubxml* souboru) z jedné instalace sady Visual Studio na jiný, můžete najít profil publikování,  *\<profilename\>.pubxml*v  *\\< projectname\>\Properties\PublishProfiles* složku pro typy spravovaných projektů. Pro moduly websites, podívejte se do části *\App_Data* složky. Publikování profilů jsou soubory XML nástroje MSBuild.

## <a name="prerequisites"></a>Požadavky

::: moniker range=">=vs-2019"

* Musíte mít Visual Studio 2019 nainstalovaný a **vývoj pro ASP.NET a web** pracovního vytížení.

    Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/) stránku a nainstalovat zdarma.
::: moniker-end

::: moniker range="vs-2017"

* Musíte mít nainstalovanou sadu Visual Studio 2017 a **vývoj pro ASP.NET a web** pracovního vytížení.

    Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/) stránku a nainstalovat zdarma.
::: moniker-end

* Vytvoření služby Azure App Service. Podrobné pokyny najdete v tématu [nasazení webové aplikace ASP.NET Core do Azure pomocí sady Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs).

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Vytvoření nového projektu ASP.NET v sadě Visual Studio

1. Na počítači se systémem Visual Studio vytvořte nový projekt.

    Výběr správné šablony. V tomto příkladu zvolte buď **webová aplikace ASP.NET (.NET Framework)** nebo (pro C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na tlačítko **OK**.

    Pokud nevidíte zadaný projekt šablony, klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí se instalační program pro Visual Studio. Nainstalujte **vývoj pro ASP.NET a web** pracovního vytížení.

    Šablona projektu zvolte (ASP.NET nebo ASP.NET Core) musí odpovídat verzi technologie ASP.NET na webovém serveru instalovat.

1. Zvolte buď **MVC** (.NET Framework) nebo **webové aplikace (Model-View-Controller)** (pro .NET Core) a ujistěte se, že **bez ověřování** je vybrána a potom klikněte na **OK**.

1. Zadejte název, například **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení** > **sestavit řešení** k sestavení projektu.

## <a name="create-the-publish-settings-file-in-azure-app-service"></a>Vytvořit soubor nastavení publikování ve službě Azure App Service

1. Na webu Azure Portal otevřete službu Azure App Service.

1. Klikněte na tlačítko **získat profil publikování** profil a uložte ho místně.

    ![Získat profil publikování](../deployment/media/tutorial-azure-app-service-get-publish-profile.png)

    Soubor s *.publishsettings* přípona souboru byl vytvořen v umístění, kam jste jej uložili. Následující kód ukazuje příklad částečného souboru (v přehlednějším formátování).

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

    Předchozí soubor *.publishsettings obvykle obsahuje dva profily publikování, které můžete použít v sadě Visual Studio, z nich se má nasadit pomocí nasazení webu a jeden pro nasazení přes FTP. Předchozí kód zobrazí profil nasazení webu. Oba profily se naimportují později při importu profilu.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Import nastavení publikování v sadě Visual Studio a nasazení

[!INCLUDE [import publish settings](../deployment/includes/import-publish-settings-vs.md)]

## <a name="next-steps"></a>Další kroky

V tomto kurzu se vytvoří soubor nastavení publikování, importovat ho do sady Visual Studio a nasazení aplikace ASP.NET do služby Azure App Service. Přehled možností publikování v sadě Visual Studio může být vhodné.

> [!div class="nextstepaction"]
> [První seznámení s nasazováním](../deployment/deploying-applications-services-and-components.md)
