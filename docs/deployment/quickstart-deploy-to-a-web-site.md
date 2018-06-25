---
title: Publikování na webu
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
- multiple
ms.openlocfilehash: ede36baefa71e352f6f7e4960403ecbaa6b304b2
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757205"
---
# <a name="publish-a-web-app-to-a-web-site-using-visual-studio"></a>Publikování webové aplikace na web pomocí sady Visual Studio

Můžete použít **publikovat** nástroj pro publikování aplikací ASP.NET, ASP.NET Core, .NET Core a Python k webu ze sady Visual Studio. Pro platformu Node.js kroky jsou podporované, ale uživatelské rozhraní se liší.

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

## <a name="publish-to-a-web-site"></a>Publikování na webu.

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat** (nebo použijte **sestavení** > **publikovat** položky nabídky).

    ![Příkaz Publikovat v místní nabídce Projekt v Průzkumníku řešení](../deployment/media/quickstart-publish.png "zvolte publikování")

1. Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Vyberte **vytvořit nový profil**.

1. V **vyberte cíl publikování** dialogovém okně vyberte **služby IIS, FTP, atd**.

    ![Zvolte služby IIS, FTP, atd.](../deployment/media/quickstart-publish-iis-ftp.png "zvolte služby IIS, FTP, atd.")

1. Vyberte **publikování**. Profil publikování nastavení, které se otevře se dialogové okno.

    ![Vyberte složku,](../deployment/media/quickstart-publish-settings-web.png "vyberte složku,")

1. V **metodu publikování** pole, jako například vybrat metodu **Web Deploy** nebo **FTP**. Nastavení, která se zobrazí vedle odpovídají způsob publikování. Nasazení webu zjednodušuje nasazení webové aplikace a weby pro servery služby IIS a musí být nainstalován jako aplikace na serveru. Použití [instalačního programu webové platformy](https://www.microsoft.com/web/downloads/platform.aspx) k její instalaci.

1. Nakonfigurujte požadovaná nastavení pro metodu publikování a vyberte **ověřit připojení**. Pokud je k dispozici server nebo cíl a správnost nastavení zprávu, která označuje, připojení se ověří a jste připraveni k publikování.

    ![Ověření připojení k](../deployment/media/quickstart-publish-web-deploy.png "ověření připojení k")

1. Vyberte **nastavení** konfigurace dalších nastavení nasazení, například zda ladění nebo verze konfigurace nasazení a potom vyberte **Uložit**. Pokud ladíte vzdáleně, není potřeba konfiguraci ladění.

1. Pokud chcete publikovat, vyberte **publikovat**. Ve výstupním okně zobrazuje průběh nasazení a výsledky.

## <a name="next-steps"></a>Další kroky

V tento rychlý start zjistili, jak pomocí sady Visual Studio k vytvoření profilu publikování. Můžete také konfigurovat publikování profil importem nastavení publikování.

> [!div class="nextstepaction"]
> [Import nastavení publikování a nasazení do služby IIS](tutorial-import-publish-settings-iis.md)
