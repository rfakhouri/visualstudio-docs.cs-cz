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
ms.openlocfilehash: b023349454f71835e13e7cc891b8be92b90c153f
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>Publikování aplikace do služby IIS pomocí importu nastavení publikování v sadě Visual Studio

Můžete použít **publikovat** nástroj k importu nastavení publikování a pak nasadíte aplikaci. V tomto článku používáme nastavení publikování pro službu IIS, ale můžete podobný postup při importu nastavení publikování pro [Azure App Service](../deployment/tutorial-import-publish-settings-azure.md). V některých scénářích použití publikování, který profil nastavení může být rychlejší než ruční konfigurace nasazení pro službu IIS pro každou instalaci sady Visual Studio.

Tento postup platí pro aplikace ASP.NET, .NET Core a ASP.NET Core v sadě Visual Studio. Kroky odpovídají Visual Studio 2017 verze 15,6 operací.

V tomto kurzu provedete následující:

> [!div class="checklist"]
> * Konfigurace služby IIS tak, aby může generovat soubor nastavení publikování
> * Vytvořte soubor nastavení publikování
> * Importovat soubor nastavení publikování do sady Visual Studio
> * Nasaďte aplikaci do služby IIS

Soubor nastavení publikování (*\*.publishsettings*) je jiný než profil publikování (*\*.pubxml*) vytvořit v sadě Visual Studio. Soubor nastavení publikování se vytvoří pomocí služby IIS nebo Azure App Service, nebo ji můžete ručně vytvořit a potom ji můžete importovat do sady Visual Studio.

> [!NOTE]
> Pokud potřebujete jenom Kopírovat sady Visual Studio publikování profilu (\*.pubxml souboru) z jedné instalace sady Visual Studio na jiný, můžete najít profil publikování,  *\<profilename\>.pubxml*, v  *\\< název projektu\>\Properties\PublishProfiles* složku pro spravovaný projekt typy. Pro weby, podívejte se do části *\App_Data* složky. Publikování profily jsou soubory nástroje MSBuild XML.

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalovanou sadu Visual Studio a **ASP.NET** a **rozhraní .NET Framework** vývoj zatížení. Pro aplikace .NET Core, musíte taky **.NET Core** zatížení.

    Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).

    Kroky v tomto článku jsou založeny na Visual Studio 2017

* Generovat soubor nastavení publikování ze služby IIS, musíte mít počítač se systémem Windows Server 2012 s rolí webového serveru IIS 8.0 správně nakonfigurovaný a nainstalována technologie ASP.NET 4.5 nebo ASP.NET Core. ASP.NET Core, najdete v části [publikování do služby IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration). Technologie ASP.NET 4.5, najdete v části [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Vytvořte nový projekt ASP.NET v sadě Visual Studio

1. V počítači s Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně vyberte buď **webové aplikace ASP.NET (rozhraní .NET Framework)** nebo (C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na **OK**.

    Pokud nevidíte šablony zadaného projektu, klikněte **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Viz požadavky v tomto článku k identifikaci požadované sadě Visual Studio úloh, které je nutné nainstalovat.

1. Vyberte buď **MVC** (rozhraní .NET Framework) nebo **webové aplikace (Model-View-Controller)** (pro .NET Core) a ujistěte se, že **bez ověřování** je vybrána a potom klikněte na **OK**.

1. Zadejte název jako **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení > Sestavit řešení** a tím projekt sestavit.

## <a name="install-and-configure-web-deploy-on-windows-server"></a>Instalace a konfigurace nasazení webu v systému Windows Server

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Vytvořte soubor nastavení publikování ve službě IIS v systému Windows Server

1. Ve službě IIS, klikněte pravým tlačítkem myši **Default Web Site**, zvolte **nasadit** > **konfigurace nasazení publikování na webu**.

    ![Nakonfigurujte konfiguraci nasazení webu](../deployment/media/tutorial-configure-web-deploy-publishing.png)

1. V **konfigurace nasazení publikování na webu** dialogové okno pole, zkontrolujte nastavení.

1. Klikněte na tlačítko **instalační program**.

    V **výsledky** panelu ukazuje výstup, které přístupová práva byl udělen zadaného uživatele a že soubor s *.publishsettings* přípona souboru byla vygenerována v uvedeném v umístění Dialogové okno.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <publishData>
      <publishProfile
        publishUrl="https://myhostname:8172/msdeploy.axd"
        msdeploySite="Default Web Site"
        destinationAppUrl="http://myhostname:80/"
        mySQLDBConnectionString=""
        SQLServerDBConnectionString=""
        profileName="Default Settings"
        publishMethod="MSDeploy"
        userName="myhostname\myusername" />
    </publishData>
    ```

    V závislosti na konfiguraci vašeho systému Windows Server a službu IIS zobrazí se různé hodnoty. Zde jsou několik podrobnosti o hodnoty, které se zobrazí:

    * *Msdeploy.axd* souboru v odkazuje `publishUrl` atribut je dynamicky generované soubor obslužné rutiny HTTP pro nasazení webu. (Pro účely testování `http://myhostname:8172` budou obecně fungovat také.)
    * `publishUrl` Port je obvykle nastavený na port 8172, což je výchozí nastavení pro nasazení webu.
    * `destinationAppUrl` Port je obvykle nastavený na portu 80, což výchozí nastavení pro službu IIS.
    * Pokud není možné se připojit ke vzdálenému hostiteli v sadě Visual Studio pomocí názvu hostitele (v následujících krocích), otestujte IP adresu místo názvu hostitele.

    > [!NOTE]
    > Pokud publikujete do IIS a běžící na virtuálním počítači Azure, nasazení webu a porty IIS musí být otevřeno ve skupině zabezpečení sítě. Podrobné informace najdete v tématu [instalace a spuštění služby IIS](/azure/virtual-machines/windows/quick-create-portal#open-port-80-for-web-traffic).

1. Zkopírujte tento soubor do počítače, kde je spuštěn nástroj Visual Studio.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Import nastavení publikování v sadě Visual Studio a nasazení

1. V počítači, kde máte projekt ASP.NET, otevřete v sadě Visual Studio, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **publikovat**.

1. Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Klikněte na tlačítko **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogové okno, klikněte na tlačítko **importovat profil**.

    ![Zvolte publikování](../deployment/media/tutorial-publish-tool-import-profile.png)

1. Přejděte do umístění souboru nastavení publikování, který jste vytvořili v předchozí části.

1. V **soubor nastavení publikování importu** dialogové okno, přejděte do a vyberte profil, který jste vytvořili v předchozí části a klikněte na tlačítko **otevřete**.

    Sada Visual Studio spustí proces nasazení a ve výstupním okně zobrazuje průběh a výsledky.

    Pokud žádné nasazení dojde k chybám, klikněte na tlačítko **nastavení** úprava nastavení. Upravit nastavení a klikněte na tlačítko **ověřením** k testování nových nastavení.

    ![Upravit nastavení v nástroji pro publikování](../deployment/media/tutorial-configure-publish-settings-in-tool.png)

## <a name="next-steps"></a>Další kroky

V tomto kurzu vytvořili soubor nastavení publikování, importovat do sady Visual Studio a nasazení aplikace ASP.NET do služby IIS.

> [!div class="nextstepaction"]
> [První seznámení s nasazováním](../deployment/deploying-applications-services-and-components.md)
