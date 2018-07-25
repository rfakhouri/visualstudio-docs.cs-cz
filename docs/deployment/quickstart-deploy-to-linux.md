---
title: Publikování do služby App Service v Linuxu
ms.custom: ''
ms.date: 07/23/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: e0268c2e65cd08274c2267ad2a4969f6015cbaf4
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233725"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Publikování aplikace ASP.NET Core do služby App Service v Linuxu pomocí sady Visual Studio

Můžete použít **publikovat** nástroj pro publikování aplikace ASP.NET Core do služby Azure App Service v Linuxu.

[!INCLUDE [quickstart-prereqs-azure-linux](includes/quickstart-prereqs-azure-linux.md)]

## <a name="publish-to-app-service-on-linux"></a>Publikování do služby App Service v Linuxu

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat** (nebo použijte **sestavení** > **publikovat** položky nabídky).

    ![Příkaz Publikovat v místní nabídce projektu v Průzkumníku řešení](../deployment/media/quickstart-publish.png "tlačítko Publikovat")

1. Pokud jste dříve nakonfigurovali všech profilů publikování **publikovat** otevře se podokno, ve které vyberte případu **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogového okna zvolte **App Service pro Linux**.

    ![Zvolte Azure App Service](../deployment/media/quickstart-publish-linux.png "zvolte služby Azure App Service")

1. Vyberte **publikovat**. **Vytvořit službu App Service** zobrazí se dialogové okno. Přihlaste se pomocí budete účet Azure, je-li nutné a výchozí nastavení aplikace služby vyplňte pole.

    ![Vytvořit službu App Service](../deployment/media/quickstart-publish-settings-app-service-linux.png "vytvořit službu Azure App Service")

1. Vyberte **vytvořit**. Visual Studio nasadí aplikaci do služby Azure App Service a webovou aplikaci se načte v prohlížeči. Vlastnosti projektu **publikovat** podokně se zobrazí adresa URL webu a další podrobnosti.

    ![Podokno vlastností zobrazuje souhrn profil publikování](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste zjistili, jak vytvořit profil publikování pro nasazení do služby App Service v Linuxu pomocí sady Visual Studio. Další informace o publikování v Linuxu pomocí Azure můžete.

> [!div class="nextstepaction"]
> [Služby App Service pro Linux](/azure/app-service/containers/app-service-linux-intro)
