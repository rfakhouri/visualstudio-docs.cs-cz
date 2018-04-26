---
title: Vytvoření vazby testovacího Kontroleru nebo testovacího agenta na síťový adaptér v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- controllers, netwrok adapter
- agents, configuring
- agents, network adapter
- controllers, configuring
ms.assetid: 7eb9290a-f9f6-4e41-9caa-796fcfaf0610
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 051b7c7375c6b13a6f3805e358645eccdc0e33c3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-bind-a-test-controller-or-test-agent-to-a-network-adapter"></a>Postupy: vytvoření vazby testovacího kontroleru nebo testovacího agenta na síťový adaptér

Pokud počítač, který má testovacího kontroleru nebo nainstalovaného softwaru agenta test má několik síťových adaptérů, musíte zadat IP adresu místo názvu počítače k identifikaci tohoto testovacího kontroleru nebo testovacího agenta.

> [!WARNING]
> Při pokusu o nastavení agenta test, může dojít k následující chybě:
>
> **Došlo k chybě 8110. Nelze se připojit k počítači zadaný kontroler nebo přístup k objektu řadiče**
>
> Tato chyba může být způsobeno instalaci řadiče test na počítači, který má více než jeden síťový adaptér. Je také možné úspěšně nainstalovat agenty a nejsou vidět tento problém, dokud pokusu o spuštění testu.

## <a name="binding-a-test-controller-to-a-specific-network-adapter"></a>Vazba testovací kontroler k určitým síťovým adaptérem

### <a name="to-obtain-the-ip-addresses-of-the-network-adapters"></a>K získání IP adresy síťových adaptérů

1.  Ze systému Windows, vyberte **spustit**, vyberte v **Zahájit hledání** zadejte **cmd**a potom zvolte **Enter**.

2.  Typ **ipconfig/all**.

     Zobrazí se IP adresy pro síťové adaptéry. Zaznamenejte IP adresu síťového adaptéru, který chcete vytvořit vazbu na vašem řadiči.

### <a name="to-bind-a-network-adapter-to-a-test-controller"></a>Vytvořit vazbu na síťový adaptér na testovací kontroler

1.  Ze systému Windows, vyberte **spustit**, vyberte v **Zahájit hledání** zadejte **services.msc**a potom zvolte **Enter**.

     **Služby** se zobrazí dialogové okno.

2.  V podokně výsledků v části **název** sloupce, klikněte pravým tlačítkem myši **Visual Studio Test Controller** služby a potom zvolte **Zastavit**.

     -nebo-

     Otevřete příkazový řádek se zvýšenými oprávněními a spusťte následující příkaz v příkazu:

     `net stop vsttcontroller`

3.  Otevřete *QTCcontroller.exe.config* konfigurační soubor XML umístěný v *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\\<edition>\Common7\IDE*.

4.  Vyhledejte `<appSettings>` značky.

    ```xml
    <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentConnectionTimeoutInSeconds" value="120"/>
      <add key="AgentSyncTimeoutInSeconds" value="300"/>
      <add key="ControllerServicePort" value="6901"/>
      <add key="ControllerUsersGroup" value="TeamTestControllerUsers"/>
      <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins"/>
      <add key="CreateTraceListener" value="no"/>
    </appSettings>
    ```

5.  Přidat `BindTo` klíč k určení síťového adaptéru, který chcete použít v `<appSettings>` oddílu.

    ```xml
            <add key="BindTo" value="<YOUR IP ADDRESS>"/>
    </appSettings>
    ```

6.  Spusťte službu testovací kontroler. Chcete-li to provést, spusťte následující příkaz na příkazovém řádku:

    `net start vsttcontroller`

    > [!WARNING]
    > Je nutné spustit instalaci agenta test znovu a agenta test připojení k řadiči. Tentokrát, zadejte IP adresu pro řadič místo názvu kontroleru.

     To platí pro kontroler, službu agent a proces agenta. `BindTo` Vlastnost musí být nastavena pro každý proces, který běží na počítači, který má více než jeden síťový adaptér. Postup pro nastavení a `BindTo` vlastnost je stejný pro všechny tři procesy, jak je uvedeno výše v tomto tématu pro testovací kontroler.

### <a name="to-bind-a-network-interface-card-to-a-test-agent"></a>Vytvořit vazbu karty síťového rozhraní s agentem Test Agent

1.  Ze systému Windows, vyberte **spustit**, vyberte v **Zahájit hledání** zadejte **services.msc**a potom zvolte **Enter**.

    **Služby** se zobrazí dialogové okno.

2.  V podokně výsledků v části **název** sloupce, klikněte pravým tlačítkem myši **Visual Studio Test Agent** služby a potom zvolte **Zastavit**.

     -nebo-

     Otevřete příkazový řádek se zvýšenými oprávněními a spusťte následující příkaz v příkazu:

     **net stop vsttagent**

3.  Otevřete *QTAgentService.exe.config* konfigurační soubor XML umístěný v *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\\<edition>\Common7\IDE*.

4.  Vyhledejte `<appSettings>` značky.

    ```xml
    <appSettings>
      <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentServicePort" value="6910"/>
      <add key="ControllerConnectionPeriodInSeconds" value="30"/>
      <add key="StopTestRunCallTimeoutInSeconds" value="120"/>
      <add key="CreateTraceListener" value="no"/>
      <add key="GetCollectorDataTimeout" value="300"/>
    </appSettings>  </appSettings>
    ```

5.  Přidat `BindTo` klíč k určení síťového adaptéru, který chcete použít v `<appSettings>` oddílu.

    ```xml
            <add key="BindTo" value="<YOUR IP ADDRESS>"/>
    </appSettings>
    ```

6.  Spusťte službu agent testu. Chcete-li to provést, spusťte následující příkaz na příkazovém řádku:

    `net start vsttagent`

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)
- [Úprava nastavení protokolování zátěžových testů](../test/modify-load-test-logging-settings.md)
- [Konfigurace portů pro testovací Kontroléry a testovací agenty](../test/configure-ports-for-test-controllers-and-test-agents.md)
- [Postupy: určení maximální velikosti souboru protokolu](../test/how-to-specify-the-maximum-size-for-the-log-file.md)
- [Postupy: nastavení časových limitů pro testovací Kontroléry a testovací agenty](../test/how-to-specify-timeout-periods-for-test-controllers-and-test-agents.md)