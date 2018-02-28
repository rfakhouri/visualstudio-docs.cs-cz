---
title: "Publikování do služby Azure App Service – Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- azure
ms.openlocfilehash: 52da1a2e618d9ececa1c8fd0d90a86e651cd7fde
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="publish-an-aspnet-or-aspnet-core-app-to-azure-app-service-using-visual-studio"></a>Publikování aplikace ASP.NET nebo ASP.NET Core Azure App Service pomocí sady Visual Studio

Můžete použít **publikovat** nástroj pro publikování aplikací ASP.NET, ASP.NET Core, Python, Node.js a .NET Core do služby Azure App Service.

Pokud již účet Azure nemáte, můžete [zaregistrujte si zde](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio).

## <a name="create-a-new-project"></a>Vytvoření nového projektu 

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně vyberte buď **webové aplikace ASP.NET (rozhraní .NET Framework)**nebo (C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na **OK**.

1. Zvolte **MVC**, ujistěte se, že **bez ověřování** je vybrána a potom klikněte na **OK**.

1. Zadejte název jako **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení > Sestavit řešení** a tím projekt sestavit.

## <a name="publish-to-azure-app-service"></a>Publikování do služby Azure App Service

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

    ![Zvolte publikování](../deployment/media/quickstart-publish-aspnet.png "zvolte publikování")

1. V **publikovat** podokně vyberte **Microsoft Azure App Service**.

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

- [Nasazení aplikace ASP.NET Core do Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)
- [Průběžné nasazování ASP.NET Core do Azure s Gitem](/aspnet/core/publishing/azure-continuous-deployment)
