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
ms.openlocfilehash: 3fa0569739ee81ec4b2aa0eec8157068ffc949cd
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63407765"
---
1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **publikovat** (pro webové formuláře **publikovat webovou aplikaci**).

    Pokud jste dříve nakonfigurovali všech profilů publikování **publikovat** otevře se podokno. Klikněte na tlačítko **nový profil**.

1. V **publikovat** dialogu **složky**, klikněte na tlačítko **Procházet**a vytvořte novou složku **C:\Publish**.

    ![RemoteDBG_Publish_Local](../media/remotedbg_publish_local.png "RemoteDBG_Publish_Local")

    Pro aplikace webových formulářů, zvolte **vlastní** v dialogovém okně Publikovat, zadejte název profilu a zvolte **OK**.

1. Klikněte na tlačítko **vytvořit profil** v rozevíracím seznamu (**publikovat** je výchozí hodnota).

1. V **publikovat** dialogové okno, klikněte na tlačítko **nastavení** propojit a pak vyberte **nastavení** kartu.

1. Nastavení konfigurace **ladění**vyberte **odstranit všechny existující soubory před publikováním**a potom klikněte na tlačítko **Uložit**.

    > [!NOTE]
    > Pokud používáte sestavení pro vydání, můžete zakázat ladění v souboru web.config, při publikování.

1. Klikněte na tlačítko **publikovat**.

    ![RemoteDBG_Publish_Debug_Config](../media/remotedbg_publish_debug_config.png "RemoteDBG_Publish_Debug_Config")

    Publikuje aplikace **ladění** konfigurace projektu do místní složky. Průběh zobrazuje v okně výstup.

1. Zkopírujte adresář projektu ASP.NET ze sady Visual Studio do místního adresáře konfigurovat pro aplikace ASP.NET (v tomto příkladu **C:\Publish**) na počítač s Windows serverem. V tomto kurzu předpokládáme, kterou kopírujete ručně, ale můžete použít jiné nástroje, jako je PowerShell, příkazu Xcopy nebo Robocopy.

    > [!CAUTION]
    > Pokud potřebujete provést změny v kódu nebo znovu sestavit, musíte znovu publikovat a opakujte tento krok. Spustitelný soubor, který jste zkopírovali do vzdáleného počítače se musí přesně odpovídat, místní zdroje a symbolů.    Pokud jste neprovádějte tuto akci, zobrazí se `cannot find or open the PDB file` upozornění v sadě Visual Studio při pokusu o ladění procesu.

1. V systému Windows Server ověřte, že aplikace spustit správně tak, že otevřete aplikaci v prohlížeči.

    Pokud aplikace nespustí správně, může být Neshoda mezi verzí technologie ASP.NET, které jsou nainstalované na serveru a váš počítač Visual Studio nebo může jít o problém s konfigurací služby IIS nebo webové stránky. Znovu zkontrolujte dřívějších krocích.
