---
title: Publikování do služby App Service v Linuxu
ms.date: 07/23/2018
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- azure
ms.openlocfilehash: 3e80f96e1af39747a6dfa9fb9737ec11bb5baf00
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54951934"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Publikování aplikace ASP.NET Core do služby App Service v Linuxu pomocí sady Visual Studio

Můžete použít **publikovat** nástroj pro publikování aplikace ASP.NET Core do služby Azure App Service v Linuxu.

Nasazení do služby App Service v Linuxu pomocí **publikovat** nástroj vyžaduje Visual Studio 2017 verze 15.7.

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
