---
title: Publikování do Azure App Service
ms.custom: ''
ms.date: 06/22/2018
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
ms.openlocfilehash: 3d15cc293f2b2b22b63e0af202bfcee8afa2cf13
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755993"
---
# <a name="publish-a-web-app-to-azure-app-service-using-visual-studio"></a>Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio

Můžete použít **publikovat** nástroj k publikování aplikace ASP.NET, jádro ASP.NET, Node.js a .NET Core pro Azure App Service a Azure App Service Linux (pomocí kontejnery). Pro aplikace, Python, postupujte podle kroků [Python - publikování do služby Azure App Service](../python/publishing-python-web-applications-to-azure-from-visual-studio.md).

[!INCLUDE [quickstart-prereqs-azure](includes/quickstart-prereqs-azure.md)]

## <a name="publish-to-azure-app-service"></a>Publikování do Azure App Service

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat** (nebo použijte **sestavení** > **publikovat** položky nabídky).

    ![Příkaz Publikovat v místní nabídce Projekt v Průzkumníku řešení](../deployment/media/quickstart-publish.png "zvolte publikování")

1. Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí, ve které případu vyberte **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogovém okně vyberte **služby App Service**.

    ![Vyberte aplikační služba Azure](../deployment/media/quickstart-publish-azure.png "vyberte aplikační služba Azure")

1. Vyberte **publikování**. **Vytvořit službu App Service** zobrazí se dialogové okno. Přihlaste se pomocí jste účet Azure, pokud nezbytné výchozí nastavení aplikace služby a vyplňte pole.

    ![Vytvoření služby App Service](../deployment/media/quickstart-publish-settings-app-service.png "vytvoření služby Azure App Service")

1. Vyberte **vytvořit**. Visual Studio nasadí aplikaci do Azure App Service a načte webové aplikace v prohlížeči. Vlastnosti projektu **publikovat** podokně se zobrazí adresa URL webu a další podrobnosti.

    ![Vlastnost podokně zobrazující Souhrn profilu publikování](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="next-steps"></a>Další kroky

V tento rychlý start zjistili, jak vytvořit profil publikování pro nasazení do Azure pomocí sady Visual Studio. Můžete také konfigurovat publikování importováním profil publikování se nastavení na Azure App Service.

> [!div class="nextstepaction"]
> [Import nastavení publikování a nasazení do Azure](tutorial-import-publish-settings-azure.md)
