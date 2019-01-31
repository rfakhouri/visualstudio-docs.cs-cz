---
title: Publikovat na web
ms.date: 01/29/2019
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 55221ea6abb93ff14c44a1b7ea190ffef9589189
ms.sourcegitcommit: e3d96b20381916bf4772f9db52b22275763bb603
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/31/2019
ms.locfileid: "55483546"
---
# <a name="publish-a-web-app-to-a-web-site-using-visual-studio"></a>Publikování webové aplikace na webu pomocí sady Visual Studio

Můžete použít **publikovat** nástroj pro publikování aplikací ASP.NET, ASP.NET Core, .NET Core a Python na web ze sady Visual Studio. Pro Node.js kroky jsou podporované, ale uživatelské rozhraní se liší.

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

> [!NOTE]
> Pokud potřebujete k publikování aplikací pro stolní počítače Windows do sdíleného síťového umístění, přečtěte si [nasazení stolní aplikace pomocí technologie ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) (C# nebo Visual Basic) nebo [nasazení nativní aplikace pomocí technologie ClickOnce](/cpp/ide/clickonce-deployment-for-visual-cpp-applications) (C++).

## <a name="publish-to-a-web-site"></a>Publikování na web

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat** (nebo použijte **sestavení** > **publikovat** položky nabídky).

    ![Příkaz Publikovat v místní nabídce projektu v Průzkumníku řešení](../deployment/media/quickstart-publish.png "tlačítko Publikovat")

1. Pokud jste dříve nakonfigurovali všech profilů publikování **publikovat** otevře se podokno. Vyberte **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogového okna zvolte **služby IIS, FTP, atd**.

    ![Zvolte službu IIS, FTP atd](../deployment/media/quickstart-publish-iis-ftp.png "zvolte službu IIS, FTP atd.")

1. Vyberte **Publikovat**. Zobrazí se dialogové okno s nastavením publikování profilu.

    ![Vyberte složku](../deployment/media/quickstart-publish-settings-web.png "výběr složky")

1. V **metodu publikování** zvolte jako metodu **Webdeploy** nebo **FTP**. Nastavení, která se zobrazí vedle odpovídají publikování metodu. Nástroj nasazení webu zjednodušuje nasazení webové aplikace a weby pro servery služby IIS a musí být nainstalovaná jako aplikace na serveru. Použití [instalačního programu webové platformy](https://www.microsoft.com/web/downloads/platform.aspx) k její instalaci.

1. Nakonfigurujte požadovaná nastavení pro metodu publikování a vyberte **ověřit připojení**. Pokud je k dispozici server nebo cíl a nastavení jsou správné, zprávu, která označuje, připojení se ověří a jste připraveni publikovat.

    ![Ověření připojení k](../deployment/media/quickstart-publish-web-deploy.png "ověření připojení k")

1. Vyberte **nastavení** nakonfigurovat další nastavení nasazení, jako je například, jestli se má nasadit konfigurace ladění nebo uvolnění a pak vyberte **Uložit**. Pokud ladíte vzdáleně, není nutná konfigurace ladění.

1. Chcete-li publikovat, vyberte **publikovat**. V okně výstupu se zobrazí nasazení průběh a výsledky.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste zjistili, jak pomocí sady Visual Studio k vytvoření profilu publikování. Můžete také nakonfigurovat publikování profilu pomocí importu nastavení publikování.

> [!div class="nextstepaction"]
> [Import nastavení publikování a nasazení do služby IIS](tutorial-import-publish-settings-iis.md)
