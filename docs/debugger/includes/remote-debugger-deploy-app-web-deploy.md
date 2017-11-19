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
ms.openlocfilehash: 27cff46f5a68ef28f247aa159a2b8be5db56b0fe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
Pokud jste nainstalovali, nasazení webu pomocí služby instalace webové platformy, můžete nasadit aplikace přímo ze sady Visual Studio.

1. Spuštění sady Visual Studio s oprávněními správce a znovu otevřít projekt.

    Pro nasazení aplikace pomocí nástroje nasazení webu jsou vyžadována oprávnění správce.

2. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **publikovat**.

3. Pro **vyberte cíl publikování**, vyberte **služby IIS, FTP, atd.** a klikněte na tlačítko **publikovat**.

    ![RemoteDBG_Publish_IISl](../media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

4. Zadejte parametry konfigurace oprava vašeho nastavení služby IIS.

    ![RemoteDBG_Publish_WebDeployl](../media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    Pokud název hostitele se nepřekládá při pokusu o ověření v další kroky **Server** textové pole, zkuste IP adresu. Zahrnout `http://` jako předpony v **Server** pole.  Nezapomeňte použít port 80 v **Server** textové pole a ujistěte se, že port 80 je otevřen v bráně firewall.

6. Klikněte na tlačítko **Další**, vyberte **ladění** konfigurace a zvolte **odebrat další soubory v cílovém umístění** pod **publikování souboru** Možnosti.

    > [!NOTE]
    > Pokud si zvolíte konfigurace verze, zakážete ladění v souboru web.config, při publikování.

5. Klikněte na tlačítko **Prev**a potom zvolte **ověřením**. Pokud nastavení připojení ověří, můžete použít k publikování.

6. Klikněte na tlačítko **publikovat** k publikování aplikace.

    Karta Výstup ukazuje, pokud publikování proběhlo úspěšně a prohlížeč pak otevře aplikace.

    Pokud dojde k chybě zmínit, Web Deploy, znovu zkontrolovat kroky instalace nasazení webu a zkontrolujte, zda jsou otevřené správné porty (nasazení webu také vyžaduje 8172 na serveru otevřen port).

    Pokud aplikace nasadí úspěšně, ale nefunguje správně, může být problém s konfigurace služby IIS, ASP.NET instalaci nebo konfiguraci webu. V systému Windows Server otevřete web ze služby IIS pro další specifické chybové zprávy a pak znovu zkontrolovat dřívějších krocích.