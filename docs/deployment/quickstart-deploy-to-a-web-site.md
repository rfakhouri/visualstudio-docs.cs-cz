---
title: "Publikování na web - Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords: deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a0b4051ce8ba14302e403cb213804b8193b60af
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="publish-a-web-app-or-a-net-core-app-to-a-web-site-using-the-visual-studio-publish-tool"></a>Publikování webu pomocí nástroje Visual Studio publikovat webovou aplikaci nebo aplikaci .NET Core

Můžete použít **publikovat** nástroj pro publikování aplikací ASP.NET pro web.

Tento postup platí pro technologii ASP.NET, ASP.NET Core, .NET Core a Python aplikace v sadě Visual Studio. Pro platformu Node.js kroky jsou podporované, ale uživatelské rozhraní se liší.

## <a name="create-a-new-project"></a>Vytvoření nového projektu 

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně vyberte buď **webové aplikace ASP.NET (rozhraní .NET Framework)**nebo (C# pouze) **webové aplikace ASP.NET Core**a potom klikněte na **OK**.

1. Zvolte **MVC**, ujistěte se, že **bez ověřování** je vybrána a potom klikněte na **OK**.

1. Zadejte název jako **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení > Sestavit řešení** a tím projekt sestavit.

## <a name="publish-to-a-web-site"></a>Publikování na webu.

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

    ![Zvolte publikování](../deployment/media/quickstart-publish-aspnet.png "zvolte publikování")

1. V **publikovat** podokně vyberte **služby IIS, FTP, atd**.

    ![Zvolte služby IIS, FTP, atd.](../deployment/media/quickstart-publish-iis-ftp.png "zvolte služby IIS, FTP, atd.")

1. Klikněte na tlačítko **publikování**.

    Profil publikování nastavení, které se otevře se dialogové okno.

    ![Vyberte složku,](../deployment/media/quickstart-publish-settings-web.png "vyberte složku,")

1. V **metodu publikování** pole, jako například vybrat metodu **Web Deploy** nebo **FTP**.

    Nastavení, která se zobrazí vedle odpovídají způsob publikování.

1. Nakonfigurujte požadovaná nastavení pro metodu publikování a klikněte na tlačítko **ověřit připojení**.

    Pokud je k dispozici server nebo cíl a správnost nastavení, zobrazí se zpráva s oznámením, připojení se ověří a jste připraveni k publikování.

    ![Ověření připojení k](../deployment/media/quickstart-publish-web-deploy.png "ověření připojení k")

1. Pokud chcete konfigurovat další nastavení nasazení, klikněte na tlačítko **nastavení**.

    Můžete nakonfigurovat možnosti, například zda ladění nebo verze konfigurace nasazení a pak klikněte na tlačítko **Uložit**. Pokud ladíte vzdáleně, není potřeba konfiguraci ladění.

1. Chcete-li publikovat, klikněte na tlačítko **publikovat**.

    Ve výstupním okně zobrazuje průběh nasazení a výsledky.

## <a name="next-steps"></a>Další kroky

- [Nasazení technologie ASP.NET do služby IIS](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)
