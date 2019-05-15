---
title: Publikování do služby IIS pomocí importu nastavení publikování
description: Vytváření a import profilu publikování k nasazení aplikace do služby IIS ze sady Visual Studio
ms.date: 01/31/2019
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8e0c7309f52fbc8056f09e5a59afcfdefaa8d0bf
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65680140"
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>Publikování aplikace do služby IIS pomocí importu nastavení publikování v sadě Visual Studio

Můžete použít **publikovat** nástroj k importu nastavení publikování a pak nasadíte aplikaci. V tomto článku používáme nastavení publikování pro službu IIS, ale můžete použít podobným způsobem k importu nastavení publikování pro [služby Azure App Service](../deployment/tutorial-import-publish-settings-azure.md). V některých scénářích použití publikování profilu nastavení může být rychlejší než ruční konfigurace nasazení do služby IIS pro každou instalaci sady Visual Studio.

Tento postup platí pro aplikace ASP.NET, ASP.NET Core a .NET Core v sadě Visual Studio.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Nakonfigurovat službu IIS tak, aby můžete vygenerovat soubor nastavení publikování
> * Vytvořit soubor nastavení publikování
> * Importovat soubor nastavení publikování do sady Visual Studio
> * Nasaďte aplikaci do služby IIS

Soubor nastavení publikování (*\*.publishsettings*) se liší od profil publikování (*\*.pubxml*) vytvořené v sadě Visual Studio. Soubor nastavení publikování se vytvoří ve službě IIS nebo Azure App Service, nebo ji můžete ručně vytvořit a pak může být importován do sady Visual Studio.

> [!NOTE]
> Pokud potřebujete jenom zkopírujte sady Visual Studio profil publikování (\*souboru .pubxml) z jedné instalace sady Visual Studio na jiný, můžete najít profil publikování,  *\<profilename\>.pubxml*, v  *\\< projectname\>\Properties\PublishProfiles* složku pro typy spravovaných projektů. Pro moduly websites, podívejte se do části *\App_Data* složky. Publikování profilů jsou soubory XML nástroje MSBuild.

## <a name="prerequisites"></a>Požadavky

::: moniker range=">=vs-2019"

* Musíte mít Visual Studio 2019 nainstalovaný a **vývoj pro ASP.NET a web** pracovního vytížení.

    Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/) stránku a nainstalovat zdarma.
::: moniker-end

::: moniker range="vs-2017"

* Musíte mít nainstalovanou sadu Visual Studio 2017 a **vývoj pro ASP.NET a web** pracovního vytížení.

    Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/) stránku a nainstalovat zdarma.
::: moniker-end

* Na serveru, musíte používat Windows Server 2012 nebo Windows Server 2016 a musí mít [role webového serveru IIS](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) správně nainstalovaný (vyžadovaných ke generování souboru nastavení publikování (*\*. publishsettings*)). ASP.NET 4.5 nebo ASP.NET Core musí také nainstalovaná na serveru. Nastavení technologie ASP.NET 4.5, naleznete v tématu [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45). ASP.NET Core, naleznete v tématu [hostitele ASP.NET Core ve Windows se službou IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration).

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Vytvoření nového projektu ASP.NET v sadě Visual Studio

1. Na počítači se systémem Visual Studio vytvořte nový projekt.

    Výběr správné šablony. V tomto příkladu zvolte buď **webová aplikace ASP.NET (.NET Framework)** nebo (pro C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na tlačítko **OK**.

    Pokud nevidíte zadaný projekt šablony, klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí se instalační program pro Visual Studio. Nainstalujte **vývoj pro ASP.NET a web** pracovního vytížení.

    Šablona projektu zvolte (ASP.NET nebo ASP.NET Core) musí odpovídat verzi technologie ASP.NET na webovém serveru instalovat.

1. Zvolte buď **MVC** (.NET Framework) nebo **webové aplikace (Model-View-Controller)** (pro .NET Core) a ujistěte se, že **bez ověřování** je vybrána a potom klikněte na **OK**.

1. Zadejte název, například **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení** > **sestavit řešení** k sestavení projektu.

## <a name="install-and-configure-web-deploy-on-windows-server"></a>Instalace a konfigurace nasazení webu v systému Windows Server

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Vytvořit soubor nastavení publikování ve službě IIS v systému Windows Server

[!INCLUDE [create-publish-settings-iis](../deployment/includes/create-publish-settings-iis.md)]

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Import nastavení publikování v sadě Visual Studio a nasazení

[!INCLUDE [import-publish-settings](../deployment/includes/import-publish-settings-vs.md)]

Jakmile se aplikace nasadí úspěšně, by se měl spustit automaticky. Pokud se nespustí ze sady Visual Studio, spusťte aplikaci ve službě IIS. Pro ASP.NET Core, budete muset Ujistěte se, že se fond aplikací pro pole **DefaultAppPool** je nastavena na **bez spravovaného kódu**.

## <a name="next-steps"></a>Další kroky

V tomto kurzu se vytvoří soubor nastavení publikování, importovat do sady Visual Studio a nasazení aplikace ASP.NET do služby IIS. Přehled o další možnosti publikování v sadě Visual Studio může být vhodné.

> [!div class="nextstepaction"]
> [První seznámení s nasazováním](../deployment/deploying-applications-services-and-components.md)
