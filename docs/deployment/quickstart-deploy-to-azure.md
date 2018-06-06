---
title: Publikování do služby Azure App Service – Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/22/2017
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: f91fd6e8c101b674b745c120978a47adb17c9b91
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765372"
---
# <a name="publish-an-aspnet-or-aspnet-core-app-to-azure-app-service-using-visual-studio"></a>Publikování aplikace ASP.NET nebo ASP.NET Core Azure App Service pomocí sady Visual Studio

Můžete použít **publikovat** nástroj pro publikování aplikací ASP.NET, ASP.NET Core, Python, Node.js a .NET Core do služby Azure App Service.

Pokud již účet Azure nemáte, můžete [zaregistrujte si zde](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio).

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalované Visual Studio 2017 a **ASP.NET a webové vývoj** pracovního vytížení a. **NET vývoj aplikací** zatížení. Pro aplikace .NET Core, musíte. **NET základní** zatížení.

    Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

## <a name="create-a-new-project"></a>Vytvoření nového projektu 

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně vyberte buď **webové aplikace ASP.NET (rozhraní .NET Framework)** nebo (C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na **OK**.

1. Zvolte **MVC** (nebo zvolte **webové aplikace (Model-View-Controller)** pro .NET Core), ujistěte se, že **bez ověřování** je vybrána a pak klikněte na tlačítko **OK** .

1. Zadejte název jako **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení > Sestavit řešení** a tím projekt sestavit.

## <a name="publish-to-azure-app-service"></a>Publikování do Azure App Service

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

    ![Zvolte publikování](../deployment/media/quickstart-publish-aspnet.png "zvolte publikování")

1. Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Klikněte na tlačítko **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogovém okně vyberte **služby App Service**.

    ![Vyberte aplikační služba Azure](../deployment/media/quickstart-publish-azure.png "vyberte aplikační služba Azure")

1. Klikněte na tlačítko **publikování**.

    **Vytvořit službu App Service** zobrazí se dialogové okno.

    ![Vytvoření služby App Service](../deployment/media/quickstart-publish-settings-app-service.png "vytvoření služby Azure App Service")
    
1. Pokud nejste v sadě Visual Studio, přihlaste se a pak výchozí nastavení aplikace služby vyplňte pole.

    Profil publikování nastavení, které se otevře se dialogové okno.

    ![Vyberte složku,](../deployment/media/quickstart-publish-settings-web.png "vyberte složku,")

    V tomto dialogovém můžete vybrat odběr, který používáte, vyberte nebo vytvořte skupinu prostředků Azure, atd.

1. Klikněte na tlačítko **vytvořit**.

    Visual Studio nasadí aplikaci do Azure App Service a načte webové aplikace v prohlížeči.

    V Souhrn **publikovat** podokně, najdete v části Adresa URL webu pro nové Azure App Service.

## <a name="next-steps"></a>Další kroky

V tento rychlý start zjistili, jak vytvořit profil publikování pro nasazení do Azure pomocí sady Visual Studio. Můžete také konfigurovat publikování importováním profil publikování se nastavení na Azure App Service.

> [!div class="nextstepaction"]
> [Import nastavení publikování a nasazení do Azure](tutorial-import-publish-settings-azure.md)
