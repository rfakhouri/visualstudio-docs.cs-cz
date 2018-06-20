---
title: Publikování na web - Visual Studio | Microsoft Docs
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
- multiple
ms.openlocfilehash: 7550c2e3b7d635d20df342558537e7a3dbd7d619
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234696"
---
# <a name="publish-a-web-app-or-a-net-core-app-to-a-web-site-using-the-visual-studio-publish-tool"></a>Publikování webu pomocí nástroje Visual Studio publikovat webovou aplikaci nebo aplikaci .NET Core

Můžete použít **publikovat** nástroj pro publikování aplikací ASP.NET pro web.

Tento postup platí pro technologii ASP.NET, ASP.NET Core, .NET Core a Python aplikace v sadě Visual Studio. Pro platformu Node.js kroky jsou podporované, ale uživatelské rozhraní se liší.

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalované Visual Studio 2017 a **ASP.NET a webové vývoj** pracovního vytížení a. **NET vývoj aplikací** zatížení. Pro aplikace .NET Core, musíte. **NET základní** zatížení.

    Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

## <a name="create-a-new-project"></a>Vytvoření nového projektu 

1. V sadě Visual Studio, vyberte **soubor** > **nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně vyberte buď **webové aplikace ASP.NET (rozhraní .NET Framework)** nebo (C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na **OK**.

1. Zvolte **MVC** (nebo zvolte **webové aplikace (Model-View-Controller)** pro .NET Core), ujistěte se, že **bez ověřování** je vybrána a pak klikněte na tlačítko **OK** .

1. Zadejte název jako **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení** > **sestavit řešení** a tím projekt sestavit.

## <a name="publish-to-a-web-site"></a>Publikování na webu.

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

    ![Zvolte publikování](../deployment/media/quickstart-publish-aspnet.png "zvolte publikování")

1. Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Klikněte na tlačítko **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogovém okně vyberte **služby IIS, FTP, atd**.

    ![Zvolte služby IIS, FTP, atd.](../deployment/media/quickstart-publish-iis-ftp.png "zvolte služby IIS, FTP, atd.")

1. Klikněte na tlačítko **publikování**.

    Profil publikování nastavení, které se otevře se dialogové okno.

    ![Vyberte složku,](../deployment/media/quickstart-publish-settings-web.png "vyberte složku,")

1. V **metodu publikování** pole, jako například vybrat metodu **Web Deploy** nebo **FTP**.

    Nastavení, která se zobrazí vedle odpovídají způsob publikování. Nasazení webu zjednodušuje nasazení webové aplikace a weby pro servery služby IIS a musí být nainstalován jako aplikace na serveru. Použití [instalačního programu webové platformy](https://www.microsoft.com/web/downloads/platform.aspx) k její instalaci.

1. Nakonfigurujte požadovaná nastavení pro metodu publikování a klikněte na tlačítko **ověřit připojení**.

    Pokud je k dispozici server nebo cíl a správnost nastavení, zobrazí se zpráva s oznámením, připojení se ověří a jste připraveni k publikování.

    ![Ověření připojení k](../deployment/media/quickstart-publish-web-deploy.png "ověření připojení k")

1. Pokud chcete konfigurovat další nastavení nasazení, klikněte na tlačítko **nastavení**.

    Můžete nakonfigurovat možnosti, například zda ladění nebo verze konfigurace nasazení a pak klikněte na tlačítko **Uložit**. Pokud ladíte vzdáleně, není potřeba konfiguraci ladění.

1. Chcete-li publikovat, klikněte na tlačítko **publikovat**.

    Ve výstupním okně zobrazuje průběh nasazení a výsledky.

## <a name="next-steps"></a>Další kroky

V tento rychlý start zjistili, jak pomocí sady Visual Studio k vytvoření profilu publikování. Můžete také konfigurovat publikování profil importem nastavení publikování.

> [!div class="nextstepaction"]
> [Import nastavení publikování a nasazení do služby IIS](tutorial-import-publish-settings-iis.md)
