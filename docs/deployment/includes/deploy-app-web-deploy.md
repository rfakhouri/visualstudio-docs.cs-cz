---
title: Nasazení pomocí nástroje nasazení webu
description: Nasazení aplikace pomocí nástroje nasazení webu v sadě Visual Studio
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 4ef232e64f308699c73c60cbe5b155f1d4ebb725
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34794223"
---
Pokud jste nainstalovali, nasazení webu pomocí služby instalace webové platformy, můžete nasadit aplikace přímo ze sady Visual Studio.

1. Spuštění sady Visual Studio s oprávněními správce a znovu otevřít projekt.

    Pro nasazení aplikace pomocí nástroje nasazení webu jsou vyžadována oprávnění správce.

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **publikovat**.

    Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Klikněte na tlačítko **nový profil**.

1. Pro **vyberte cíl publikování**, vyberte **služby IIS, FTP, atd.** a klikněte na tlačítko **publikovat**.

    ![RemoteDBG_Publish_IISl](../../debugger/media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

1. Zadejte parametry konfigurace oprava vašeho nastavení služby IIS.

    ![RemoteDBG_Publish_WebDeployl](../../debugger/media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    Pokud název hostitele se nepřekládá při pokusu o ověření v další kroky **Server** textové pole, zkuste IP adresu. Zahrnout `http://` jako předpony v **Server** pole.  Nezapomeňte použít port 80 v **Server** textové pole a ujistěte se, že jsou otevřené v bráně firewall port 80 a port 8172.

1. Zvolte **ověření**. Pokud nastavení připojení ověří, můžete použít k publikování.

1. Klikněte na tlačítko **publikovat** k publikování aplikace.

    Karta Výstup ukazuje, pokud publikování proběhlo úspěšně a prohlížeč pak otevře aplikace.

    Pokud dojde k chybě zmínit, Web Deploy, znovu zkontrolovat kroky instalace nasazení webu a zkontrolujte, zda jsou otevřené správné porty (nasazení webu také vyžaduje 8172 na serveru otevřen port).

    Pokud aplikace nasadí úspěšně, ale nefunguje správně, může být problém s konfigurace služby IIS, ASP.NET instalaci nebo konfiguraci webu. V systému Windows Server otevřete web ze služby IIS pro další specifické chybové zprávy a pak znovu zkontrolovat dřívějších krocích.
