---
title: Časových limitů pro testovací Kontroléry a testovací agenty v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- agents, configuring
- agetns, timeouts
- controllers, configuring
- controllers, timeouts
ms.assetid: 777d0db5-0073-458a-a2a3-58b1c1f24c60
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 444c4e7214d55aad270a88325ee9e694e84987c6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31979045"
---
# <a name="how-to-specify-timeout-periods-for-test-controllers-and-test-agents"></a>Postupy: Nastavení časových limitů pro testovací kontroléry a testovací agenty

Testovací kontroler a agenta test mít několik nastavení časového limitu, které určují, jak dlouho má čekat na odpovědi od sebe navzájem nebo ze zdroje dat, než selže s chybou. Za určitých okolností může být potřeba upravit hodnoty časového limitu tak, aby vyhovovaly vaší topologie nebo jiných problémů, prostředí. Chcete-li upravit hodnoty časového limitu, upravte konfigurační soubor XML, který je přidružený ke testovacího kontroleru nebo testovacího agenta, jak je popsané v následujících postupech.

 Chcete-li upravit testovacího kontroleru nebo testovacího agenta různá nastavení časového limitu, upravte následující konfigurační soubory pomocí názvy klíčů a hodnot v tabulkách:

-   Testovací kontroler: QTController.exe.config

    |Název klíče|Popis|Hodnota|
    |--------------|-----------------|-----------|
    |AgentConnectionTimeoutInSeconds|Počet sekund čekání na požadavek ping agenta považuje za připojení ztraceno.|"n" sekund.|
    |AgentSyncTimeoutInSeconds|Při spuštění synchronizace testovací běh, kolik sekund se má čekat na všechny agenty k synchronizaci před ukončením spustit.|"n" sekund.|
    |AgentInitializeTimeout|Počet sekund pro čekání, pro všechny agenty a jejich sběrače dat k chybě při inicializaci na začátku testu spustit před ukončením testovacím běhu. Tato hodnota by měla být přiměřeně velká, pokud používáte dat.|"n" sekund. Výchozí hodnota: "120" (dvou minut).|
    |AgentCleanupTimeout|Počet sekund pro čekání, pro všechny agenty a jejich sběrače dat vymazání, před dokončením test spustit. Tato hodnota by měla být přiměřeně velká, pokud používáte dat.|"n" sekund. Výchozí hodnota: "120" (dvou minut).|

-   Testovací Agent: QTAgentService.exe.config

    |Název klíče|Popis|Hodnota|
    |--------------|-----------------|-----------|
    |ControllerConnectionPeriodInSeconds|Počet sekund mezi jednotlivými pokusy o připojení k řadiči.|"n" sekund. Výchozí hodnota: "30" (30 sekund).|
    |RemotingTimeoutSeconds|Maximální dobu v sekundách může poslední volání vzdálené komunikace.|"n" sekund. Výchozí hodnota: "600" (deset minut).|
    |StopTestRunCallTimeoutInSeconds|Počet sekund čekání na zastavení testu spusťte volání.|"n" sekund. Výchozí hodnota: "120" (dvou minut).|
    |GetCollectorDataTimeout|Počet sekund pro čekání dat kolekce.|"n" sekund. Výchozí hodnota: "300" (pěti minut).|

## <a name="to-specify-agent-timeout-options-for-a-test-controller"></a>Postup určení možností vypršení časového limitu agenta pro testovací kontroler

1. Otevřete konfigurační soubor QTCcontroller.exe.config XML nachází v % ProgramFiles(x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE.

2. Vyhledejte `<appSettings>` značky.

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

3. Upravte existující hodnoty pro jeden z klíčů časový limit testu řadiče. Například můžete změnit výchozí hodnotu pro klíč `AgentConnectionTimeoutInSeconds` ze dvou minut až tři minut:

    ```xml
    <add key="AgentConnectionTimeoutInSeconds" value="180"/>
    ```

    -nebo-

    Přidejte další klíč a zadejte hodnotu časového limitu. Například můžete přidat `AgentInitializeTimeout` klíče v `<appSettings>` části a zadat hodnotu pět minut:

    ```xml
    <appSettings>
            <add key="AgentInitializeTimeout" value="300"/>
    </appSettings>
    ```

## <a name="to-specify-agent-timeout-options-for-a-test-agent"></a>Postup určení možností vypršení časového limitu agenta Test Agent

1. Otevřete konfigurační soubor QTAgentService.exe.config XML nachází v % ProgramFiles(x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE.

2. Vyhledejte `<appSettings>` značky.

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

3. Upravte existující hodnoty pro jeden z klíčů agentem test agent časový limit. Například můžete změnit výchozí hodnotu pro klíč `ControllerConnectionPeriodInSeconds` z 30 sekund na jednu minutu:

    ```xml
    <add key="ControllerConnectionPeriodInSeconds" value="60"/>
    ```

    -nebo-

    Přidejte další klíč a zadejte hodnotu časového limitu. Například můžete přidat `RemotingTimeoutSeconds` klíče v `<appSettings>` části a zadejte hodnotu 15 minut:

    ```xml
    <appSettings>
            <add key=" RemotingTimeoutSeconds " value="900"/>
    </appSettings>
    ```

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)
- [Úprava nastavení protokolování zátěžových testů](../test/modify-load-test-logging-settings.md)
- [Konfigurace portů pro testovací Kontroléry a testovací agenty](../test/configure-ports-for-test-controllers-and-test-agents.md)
- [Postupy: určení maximální velikosti souboru protokolu](../test/how-to-specify-the-maximum-size-for-the-log-file.md)
- [Postupy: vytvoření vazby testovacího Kontroleru nebo testovacího agenta na síťový adaptér](../test/how-to-bind-a-test-controller-or-test-agent-to-a-network-adapter.md)