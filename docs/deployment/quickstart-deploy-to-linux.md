---
title: Publikování do služby App Service v Linuxu
ms.date: 01/29/2019
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- azure
ms.openlocfilehash: 12d1df3874388f0c113600e20ca2dbd080d15d10
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62899113"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Publikování aplikace ASP.NET Core do služby App Service v Linuxu pomocí sady Visual Studio

Spouští se v sadě Visual Studio 2017 verze 15.7, můžete publikovat aplikace ASP.NET Core do Azure App Service pro Linux (pomocí kontejnerů) pomocí některého z následujících metod.

* Průběžné (nebo automatizované) nasazení aplikací, použijte Azure DevOps s využitím [kanály Azure](https://docs.microsoft.com/azure/devops/pipelines/get-started-yaml?view=azdevops).

* Pro jednorázové (nebo ruční) nasazení aplikací, použijte **publikovat** nástroje v sadě Visual Studio k publikování aplikace ASP.NET Core do služby App Service pro Linux (použitím kontejnery).

Tento článek popisuje způsob použití **publikovat** nástroj pro jednorázové nasazení.

[!INCLUDE [quickstart-prereqs-azure-linux](includes/quickstart-prereqs-azure-linux.md)]

## <a name="publish-to-app-service-on-linux"></a>Publikování do služby App Service v Linuxu

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat** (nebo použijte **sestavení** > **publikovat** položky nabídky).

    ![Příkaz Publikovat v místní nabídce projektu v Průzkumníku řešení](../deployment/media/quickstart-publish.png "tlačítko Publikovat")

1. Pokud jste dříve nakonfigurovali všech profilů publikování **publikovat** otevře se podokno, ve které vyberte případu **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogového okna zvolte **App Service pro Linux**.

    ![Zvolte Azure App Service](../deployment/media/quickstart-publish-linux.png "zvolte služby Azure App Service")

1. Vyberte **Publikovat**. **Vytvořit službu App Service** zobrazí se dialogové okno. Přihlaste se pomocí budete účet Azure, je-li nutné a výchozí nastavení aplikace služby vyplňte pole.

    ![Vytvořit službu App Service](../deployment/media/quickstart-publish-settings-app-service-linux.png "vytvořit službu Azure App Service")

1. Vyberte **Vytvořit**. Visual Studio nasadí aplikaci do služby Azure App Service a webovou aplikaci se načte v prohlížeči. Vlastnosti projektu **publikovat** podokně se zobrazí adresa URL webu a další podrobnosti.

    ![Podokno vlastností zobrazuje souhrn profil publikování](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="clean-up-resources"></a>Vyčištění prostředků

V předchozích krocích jste vytvořili prostředky Azure ve skupině prostředků. Pokud jste Neočekáváme, že v budoucnu potřeba tyto prostředky, můžete je odstranit tak, že odstraníte skupinu prostředků.
V nabídce vlevo na webu Azure Portal vyberte **skupiny prostředků** a pak vyberte **myResourceGroup**.
Na stránce skupiny prostředků Ujistěte se, že všechny uvedené prostředky jsou ty, které chcete odstranit.
Vyberte **odstranit**, typ **myResourceGroup** v textovém poli a pak vyberte **odstranit**.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste zjistili, jak vytvořit profil publikování pro nasazení do služby App Service v Linuxu pomocí sady Visual Studio. Další informace o publikování v Linuxu pomocí Azure můžete.

> [!div class="nextstepaction"]
> [Služby App Service pro Linux](/azure/app-service/containers/app-service-linux-intro)
