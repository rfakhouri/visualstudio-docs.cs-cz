---
title: Nasazení kontejneru Dockeru ASP.NET Core do služby Azure App Service | Dokumentace Microsoftu
description: Další informace o použití nástroje kontejneru sady Visual Studio k nasazení webové aplikace ASP.NET Core do služby Azure App Service
author: ghogen
manager: jillfra
ms.technology: vs-azure
ms.devlang: dotnet
ms.topic: article
ms.date: 03/08/2019
ms.author: ghogen
ms.openlocfilehash: 8dfb41e9e5e24c01b2973c3d743897329a3a115e
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59648086"
---
# <a name="deploy-an-aspnet-core-container-to-azure-app-service-using-visual-studio"></a>Nasazení kontejneru ASP.NET Core do služby Azure App Service pomocí sady Visual Studio

Tento kurz vás provede použitím sady Visual Studio k publikování kontejnerizované webové aplikace ASP.NET Core do [služby Azure App Service](/azure/app-service). Azure App Service je příslušnou službu pro jeden kontejner webové aplikace hostované v Azure.

Pokud ještě nemáte předplatné Azure, vytvořte si [bezplatný účet](https://azure.microsoft.com/free/dotnet/?utm_source=acr-publish-doc&utm_medium=docs&utm_campaign=docs) před tím, než začnete.

## <a name="prerequisites"></a>Požadavky

K provedení kroků v tomto kurzu je potřeba:

::: moniker range="vs-2017"
- Nainstalujte nejnovější verzi [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) s úlohou "vývoj aplikací ASP.NET a web"
::: moniker-end
::: moniker range=">=vs-2019"
- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) s *vývoj pro ASP.NET a web* pracovního vytížení.
::: moniker-end
- Nainstalujte [Desktop Dockeru](https://docs.docker.com/docker-for-windows/install/)

## <a name="create-an-aspnet-core-web-app"></a>Vytvoření webové aplikace ASP.NET Core

Následující kroky vás provedou vytvořením základní aplikaci ASP.NET Core, který se použije v tomto kurzu.

::: moniker range="vs-2017"
1. V nabídce sady Visual Studio vyberte **soubor > Nový > projekt**.
2. V části **šablony** část **nový projekt** dialogu **Visual C# > Web**.
3. Vyberte **webová aplikace ASP.NET Core**.
4. Pojmenujte novou aplikaci (nebo přijmout výchozí nastavení) a vyberte **OK**.
5. Vyberte **webovou aplikaci**.
6. Zkontrolujte, **povolit podporu Dockeru** zaškrtávací políčko.
7. Vyberte **Linux** typ kontejneru a klikněte na tlačítko **OK**. Kontejnery Windows nejsou podporovány pro nasazení do služby Azure App Service jako kontejner.
::: moniker-end
::: moniker range=">= vs-2019"
1. V okně spuštění sady Visual Studio zvolte **vytvořte nový projekt**.
1. Zvolte **webové aplikace ASP.NET Core**a zvolte **Další**.
1. Pojmenujte novou aplikaci (nebo přijmout výchozí nastavení) a zvolte **vytvořit**.
1. Zvolte **webovou aplikaci**.
1. Vyberte, jestli chcete podpora protokolu SSL pomocí **konfigurace pro protokol HTTPS** zaškrtávací políčko.
1. Zkontrolujte, **povolit podporu Dockeru** zaškrtávací políčko.
1. Vyberte **Linux** typ kontejneru a klikněte na tlačítko **vytvořit**. Kontejnery Windows nejsou podporovány pro nasazení do služby Azure App Service jako kontejner.
::: moniker-end

## <a name="deploy-the-container-to-azure"></a>Nasazení kontejneru do Azure

1. Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a zvolte **publikovat**.
1. V dialogovém okně cíl publikování zvolte **App Service pro Linux**.
1. Můžete publikovat jenom do služby App Service, nebo můžete publikovat do služby App Service a Azure Container Registry (ACR). Chcete-li publikovat kontejneru v Azure Container Registry (ACR), zvolte **vytvořit novou službu App Service pro kontejnery**a klikněte na tlačítko **publikovat**.

   ![Snímek obrazovky dialogového okna publikování](media/deploy-app-service/publish-app-service-linux.PNG)

   Chcete-li publikovat jenom do služby Azure App Service bez pomocí služby Azure Container Registry, zvolte **vytvořit nový**a klikněte na tlačítko **publikovat**.

1. Zkontrolujte, že jste přihlášení pomocí účtu, který je spojen s vaším předplatným Azure a zvolte jedinečný název, předplatné, skupinu prostředků, plán hostování a registr (pokud existuje) nebo přijměte výchozí hodnoty.

   ![Snímek obrazovky s nastavením publikování](media/deploy-app-service/publish-app-service-linux2.png)

1. Zvolte **Vytvořit**. Váš kontejner nasadí do služby Azure v registru prostředku skupiny a kontejner, kterou jste vybrali. Tento proces trvá hodně času. Když se dokončí, **publikovat** kartu s informacemi o co byla publikována, včetně adresy URL webu.

   ![Snímek obrazovky s kartou publikovat](media/deploy-app-service/publish-succeeded.PNG)

1. Klikněte na odkaz lokality zkontrolujte, jestli vaše aplikace funguje očekávaným způsobem v Azure.

   ![Snímek obrazovky webové aplikace](media/deploy-app-service/web-application-running.png)

1. Profil publikování se uloží všechny podrobnosti, které jste vybrali, jako je například registru prostředku skupiny a kontejner.
1. Znovu nasadit s stejný profil publikování, použijte **publikovat** tlačítko, **publikovat** tlačítko **aktivita publikování webu** okno, nebo klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a zvolte **publikovat** položku v kontextové nabídce.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud chcete odebrat všechny prostředky Azure, které jsou spojené s tímto kurzem, odstraňte skupinu prostředků pomocí [webu Azure portal](https://portal.azure.com). Chcete-li najít skupinu prostředků, které jsou přidružené k publikované webové aplikaci, zvolte **zobrazení** > **ostatní Windows** > **aktivita publikování webu**, a potom vyberte ikonu ozubeného kola. **Publikovat** kartě se otevře, která obsahuje skupiny prostředků.

Na webu Azure Portal, zvolte **skupiny prostředků**, vyberte skupinu prostředků, otevřete její stránku Podrobnosti. Ověřte, že se jedná o správnou skupinu a klikněte na tlačítko **odebrání skupiny prostředků**, zadejte název a zvolte **odstranit**.

## <a name="next-steps"></a>Další kroky

Nastavení průběžné integrace a doručování (CI/CD) s [kanály Azure](/azure/devops/pipelines/?view=azure-devops).

## <a name="see-also"></a>Viz také:

[Nasazení do služby Azure Container Registry](vs-azure-tools-docker-hosting-web-apps-in-docker.md)