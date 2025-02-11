---
title: Nasazení kontejneru ASP.NET Core Docker do Azure App Service | Microsoft Docs
description: Naučte se používat nástroje sady Visual Studio Container k nasazení ASP.NET Core webové aplikace do Azure App Service
author: ghogen
manager: jillfra
ms.technology: vs-azure
ms.devlang: dotnet
ms.topic: article
ms.date: 03/08/2019
ms.author: ghogen
ms.openlocfilehash: 9431046c57851e31a3711b4785f9cce45acab45f
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70179875"
---
# <a name="deploy-an-aspnet-core-container-to-azure-app-service-using-visual-studio"></a>Nasazení kontejneru ASP.NET Core pro Azure App Service pomocí sady Visual Studio

V tomto kurzu se seznámíte s použitím sady Visual Studio k publikování ASP.NET Core webové aplikace s využitím kontejnerů do [Azure App Service](/azure/app-service). Azure App Service je vhodná služba pro webovou aplikaci s jedním kontejnerem, která je hostovaná v Azure.

Pokud ještě nemáte předplatné Azure, vytvořte si [bezplatný účet](https://azure.microsoft.com/free/dotnet/?utm_source=acr-publish-doc&utm_medium=docs&utm_campaign=docs) před tím, než začnete.

## <a name="prerequisites"></a>Požadavky

K provedení kroků v tomto kurzu je potřeba:

::: moniker range="vs-2017"
- Nainstalujte si nejnovější verzi sady [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) s úlohou vývoj ASP.NET a webu.
::: moniker-end
::: moniker range=">=vs-2019"
- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) s úlohou *vývoje ASP.NET a webu* .
::: moniker-end
- Nainstalovat [Docker Desktop](https://docs.docker.com/docker-for-windows/install/)

## <a name="create-an-aspnet-core-web-app"></a>Vytvoření webové aplikace v ASP.NET Core

Následující kroky vás provedou vytvořením základní aplikace ASP.NET Core, která se bude používat v tomto kurzu.

::: moniker range="vs-2017"
1. V nabídce aplikace Visual Studio vyberte **soubor > nový > projekt**.
2. V části **šablony** v dialogovém okně **Nový projekt** vyberte **Visual C# > Web**.
3. Vyberte **webová aplikace ASP.NET Core**.
4. Dejte nové aplikaci název (nebo pojmenujte výchozí) a vyberte **OK**.
5. Vyberte **webovou aplikaci**.
6. Zaškrtněte políčko **Povolit podporu Docker** .
7. Vyberte typ kontejneru **Linux** a klikněte na tlačítko **OK**. Nasazení kontejnerů Windows do Azure App Service jako kontejneru se nepodporuje.
::: moniker-end
::: moniker range=">= vs-2019"
1. V okně Start sady Visual Studio vyberte možnost **vytvořit nový projekt**.
1. Vyberte **ASP.NET Core webová aplikace**a klikněte na tlačítko **Další**.
1. Dejte nové aplikaci název (nebo pojmenujte výchozí) a vyberte **vytvořit**.
1. Vyberte možnost **Webová aplikace**.
1. Určete, jestli chcete, aby podpora SSL používala zaškrtávací políčko **Konfigurovat pro protokol HTTPS** .
1. Zaškrtněte políčko **Povolit podporu Docker** .
1. Vyberte typ kontejneru **Linux** a klikněte na **vytvořit**. Nasazení kontejnerů Windows do Azure App Service jako kontejneru se nepodporuje.
::: moniker-end

## <a name="deploy-the-container-to-azure"></a>Nasazení kontejneru do Azure

1. V **Průzkumník řešení** klikněte pravým tlačítkem na projekt a vyberte **publikovat**.
1. V dialogovém okně Publikovat cíl vyberte možnost **App Service Linux**.
1. Můžete publikovat pouze pro App Service, nebo můžete publikovat do App Service a Azure Container Registry (ACR). Chcete-li publikovat kontejner v Azure Container Registry (ACR), vyberte možnost **vytvořit novou App Service pro kontejnery**a klikněte na tlačítko **publikovat**.

   ![Snímek obrazovky s dialogovým oknem pro publikování](media/deploy-app-service/publish-app-service-linux.PNG)

   Chcete-li publikovat pouze do Azure App Service bez použití Azure Container Registry, vyberte možnost **vytvořit nový**a klikněte na tlačítko **publikovat**.

1. Ověřte, že jste přihlášeni pomocí účtu, který je přidružený k vašemu předplatnému Azure, a vyberte jedinečný název, předplatné, skupinu prostředků, plán hostování a registr kontejnerů (Pokud je k dispozici) nebo přijměte výchozí hodnoty.

   ![Snímek obrazovky s nastavením publikování](media/deploy-app-service/publish-app-service-linux2.png)

1. Zvolte **Vytvořit**. Váš kontejner se do Azure nasadí v rámci skupiny prostředků a registru kontejneru, který jste vybrali. Tento proces trvá trochu času. Po dokončení se na kartě **publikovat** zobrazí informace o tom, co bylo publikováno, včetně adresy URL webu.

   ![Snímek obrazovky s kartou publikovat](media/deploy-app-service/publish-succeeded.PNG)

1. Kliknutím na odkaz lokalita ověříte, že aplikace funguje podle očekávání v Azure.

   ![Snímek obrazovky webové aplikace](media/deploy-app-service/web-application-running.png)

1. Profil publikování se uloží se všemi podrobnostmi, které jste vybrali, například skupiny prostředků a registru kontejnerů.
1. Chcete-li znovu nasadit se stejným publikačním profilem, použijte tlačítko **publikovat** v okně **aktivity publikování webu** nebo klikněte pravým tlačítkem myši na projekt v **Průzkumník řešení** a vyberte položku **publikovat** na Kontextová nabídka

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud chcete odebrat všechny prostředky Azure přidružené k tomuto kurzu, odstraňte skupinu prostředků pomocí [Azure Portal](https://portal.azure.com). Chcete-li najít skupinu prostředků přidruženou k publikované webové aplikaci, zvolte možnost **Zobrazit** > další**webovou aktivitu publikování** **systému Windows** > a pak zvolte ikonu ozubeného kolečka. Otevře se karta **publikovat** , která obsahuje skupinu prostředků.

V Azure Portal zvolte **skupiny prostředků**, vyberte skupinu prostředků a otevřete její stránku s podrobnostmi. Ověřte, jestli se jedná o správnou skupinu prostředků, a pak zvolte **Odebrat skupinu prostředků**, zadejte název a zvolte **Odstranit**.

## <a name="next-steps"></a>Další postup

Pomocí [Azure Pipelines](/azure/devops/pipelines/?view=azure-devops)nastavte průběžnou integraci a doručování (CI/CD).

## <a name="see-also"></a>Viz také:

[Nasadit do Azure Container Registry](vs-azure-tools-docker-hosting-web-apps-in-docker.md)