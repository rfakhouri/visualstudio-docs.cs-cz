---
title: Nasazení do místní složky
description: Nasazení aplikace do místní složky
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: bd477fec033eb75f626401586abfd10c798601ef
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
---
1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **publikovat** (pro webové formuláře **publikování webové aplikace**).

    Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Klikněte na tlačítko **nový profil**.

1. V **publikovat** dialogové okno, vyberte **složky**, klikněte na tlačítko **Procházet**a vytvořte novou složku, **C:\Publish**.

    ![RemoteDBG_Publish_Local](../media/remotedbg_publish_local.png "RemoteDBG_Publish_Local")

    Pro aplikace webových formulářů, zvolte **vlastní** v dialogovém okně Publikovat zadejte název profilu a vyberte **OK**.

1. Klikněte na tlačítko **vytvořit profil** v rozevíracím seznamu (**publikovat** je výchozí hodnota).

1. V **publikovat** dialogové okno, klikněte na tlačítko **nastavení** propojit a pak vyberte **nastavení** kartě.

1. Nastavte konfiguraci na **ladění**, vyberte **odstranit všechny existující soubory před publikováním**a potom klikněte na **Uložit**.

    > [!NOTE]
    > Pokud používáte sestavení pro vydání, můžete zakázat ladění v souboru web.config, při publikování.

1. Klikněte na tlačítko **publikování**.

    ![RemoteDBG_Publish_Debug_Config](../media/remotedbg_publish_debug_config.png "RemoteDBG_Publish_Debug_Config")
    
    Publikuje aplikace **ladění** konfigurace projektu do místní složky. Průběh zobrazuje v okně výstupu.

1. Kopírování adresáři projektu ASP.NET z počítače, Visual Studio do místního adresáře konfigurovat pro aplikace ASP.NET (v tomto příkladu **C:\Publish**) v počítači Windows serveru. V tomto návodu předpokládáme kopírujete ručně, ale můžete použít jiné nástroje, například prostředí PowerShell, Xcopy nebo Robocopy.

    > [!CAUTION]
    >  Pokud potřebujete provést změny kódu nebo opětovné sestavení, musíte znovu publikovat a opakujte tento krok. Spustitelný soubor, který jste zkopírovali ke vzdálenému počítači se musí přesně shodovat místního zdroje a symboly.    Pokud neprovedete tento obdržíte `cannot find or open the PDB file` upozornění v sadě Visual Studio, při pokusu o ladění proces.

1. V systému Windows Server ověřte, zda aplikace spustit správně otevřením aplikace v prohlížeči.

    Pokud aplikace nefunguje správně, může být Neshoda mezi verzi technologie ASP.NET nainstalován na váš server a Visual Studio počítači nebo může jít o problém s konfigurací služby IIS nebo na webovém serveru. Znovu zkontrolujte dřívějších krocích.
