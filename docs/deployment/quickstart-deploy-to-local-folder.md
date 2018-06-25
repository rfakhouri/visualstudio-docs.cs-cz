---
title: Nasazení do místní složky
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, local folder
ms.assetid: adb461c4-812a-4b8c-b2ab-96002379f6a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 517698aa2e042d74138579dae3633930b338cd61
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756272"
---
# <a name="deploy-an-app-to-a-local-folder-using-visual-studio"></a>Nasazení aplikace do místní složky pomocí sady Visual Studio

Můžete použít **publikovat** nástroj pro publikování aplikací ASP.NET, ASP.NET Core, .NET Core a Python do místní složky ze sady Visual Studio. Pro platformu Node.js kroky jsou podporované, ale uživatelské rozhraní se liší.

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

## <a name="deploy-to-a-local-folder"></a>Nasazení do místní složky

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat** (nebo použijte **sestavení** > **publikovat** položky nabídky).

    ![Příkaz Publikovat v místní nabídce Projekt v Průzkumníku řešení](../deployment/media/quickstart-publish.png "zvolte publikování")

1. Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Vyberte **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogovém okně vyberte **složky**.

    ![Vyberte jako typ publikovat místní složky](../deployment/media/quickstart-publish-folder.png "vybrat složku")

1. Zadejte cestu nebo vyberte **Procházet** zadat do místní složky.

1. Vyberte **publikování**. Visual Studio vytvoří projekt a publikuje do zadané složky. Vlastnosti projektu **publikovat** podokně se zobrazí, zobrazující profil souhrnu.

    ![Vlastnost podokně zobrazující Souhrn profilu publikování](../deployment/media/quickstart-publish-folder-summary.png)

1. Chcete-li konfigurovat nastavení nasazení, vyberte **konfigurace** v profilu přehled a vyberte **nastavení** kartě.

    ![Nastavení profilu](../deployment/media/quickstart-profile-settings.png "nastavení profilu")

1. Konfigurovat možnosti, například zda ladění nebo verze konfigurace nasazení a potom vyberte **Uložit**.

1. Chcete-li znovu publikovat, vyberte **publikovat**.

Publikované soubory žádným způsobem, který chcete nasaďte. Například je do balíčků *.zip* souboru, použijte příkaz jednoduché kopírování nebo nasadit pomocí jakékoli instalačního balíčku podle svého výběru.

## <a name="next-steps"></a>Další kroky

- [Nasazení aplikace .NET Core pomocí nástroje Publish](/dotnet/core/deploying/deploy-with-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Balíček desktopové aplikace pro Microsoft Store (přemostění na desktop)](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- (.NET) [Nasazení rozhraní .NET Framework a aplikace](/dotnet/framework/deployment/)
