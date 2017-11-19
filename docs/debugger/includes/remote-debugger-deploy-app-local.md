---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: a55b2a12c9a45c5a3952e3e6f4e1627bec8ba520
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **publikovat** (pro webové formuláře **publikování webové aplikace**).

2. V **publikovat** dialogové okno, vyberte **složky**, klikněte na tlačítko **Procházet**a vytvořte novou složku, **C:\Publish**.

    ![RemoteDBG_Publish_Local](../media/remotedbg_publish_local.png "RemoteDBG_Publish_Local")

    Pro aplikace webových formulářů, zvolte **vlastní** v dialogovém okně Publikovat zadejte název profilu a vyberte **OK**.

3. Klikněte na tlačítko **publikování**.

    Visual Studio publikuje projektu do složky. Průběh zobrazuje v okně výstupu.

4. V **publikovat** dialogové okno, klikněte na tlačítko **nastavení** propojit a pak vyberte **nastavení** kartě.

5. Nastavte konfiguraci na **ladění**, vyberte **odstranit všechny existující soubory před publikováním**a potom klikněte na **Uložit**.

    > [!NOTE]
    > Pokud používáte sestavení pro vydání, můžete zakázat ladění v souboru web.config, při publikování.

6. Klikněte na tlačítko **publikování**.

    ![RemoteDBG_Publish_Debug_Config](../media/remotedbg_publish_debug_config.png "RemoteDBG_Publish_Debug_Config")
    
    Publikuje aplikace **ladění** konfigurace projektu do místní složky.

5. Kopírování adresáři projektu ASP.NET z počítače, Visual Studio do místního adresáře konfigurovat pro aplikace ASP.NET (v tomto příkladu **C:\Publish**) v počítači Windows serveru. V tomto návodu předpokládáme kopírujete ručně, ale můžete použít jiné nástroje, například prostředí PowerShell, Xcopy nebo Robocopy.

    > [!CAUTION]
    >  Pokud potřebujete provést změny kódu nebo opětovné sestavení, musíte znovu publikovat a opakujte tento krok. Spustitelný soubor, který jste zkopírovali ke vzdálenému počítači se musí přesně shodovat místního zdroje a symboly.

6. V systému Windows Server ověřte, zda aplikace spustit správně otevřením aplikace v prohlížeči.

    Pokud aplikace nefunguje správně, může být Neshoda mezi verzi technologie ASP.NET nainstalován na váš server a Visual Studio počítači nebo může jít o problém s konfigurací služby IIS nebo na webovém serveru. Znovu zkontrolujte dřívějších krocích.