---
title: "Řešení potíží s testovacích Kontrolérů a testovacích agentů v sadě Visual Studio | Microsoft Docs"
ms.date: 10/20/2016
ms.topic: article
helpviewer_keywords:
- load tests, test controllers
- load tests, troubleshooting
- load tests, test agents
- troubleshooting, test controllers and agents in load tests
ms.assetid: 77329348-3a5d-43de-b6cb-90f93296a081
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 37ff6e82c61e55dc162287ce944008cc09e37204
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="strategies-for-troubleshooting-test-controllers-and-test-agents-in-load-tests"></a>Strategie řešení potíží s testovacími kontroléry a testovacími agenty v zátěžových testech

Tento článek popisuje některé běžné problémy, ke kterým může dojít při práci s testovacích kontrolérů a testovacích agentů v sadě Visual Studio.

##  <a name="unable-to-collect-performance-counters-on-test-agent-computer"></a>Nelze získat čítače výkonu v počítači agenta Test

 Když spustíte zátěžový test, může být, zobrazí se chyba při pokusu o připojení k na testovacím počítači agenta a shromažďování čítačů výkonu. Služba Remote Registry je služba zajišťuje data čítače výkonu ke vzdálenému počítači. U některých operačních systémů služba Remote Registry se nespustí automaticky. Chcete-li tento problém vyřešit, ručně spusťte službu Remote Registry.

> [!NOTE]
>  Dostanete služba Remote Registry v **ovládací panely.** Zvolte **nástroje pro správu** a potom zvolte **služby**.

 Další příčinou tohoto problému je, že nemáte dostatečná oprávnění ke čtení čítačů výkonu. Místní testovacích bězích účet uživatele, který spouští test musí být členem skupiny Power Users nebo vyšší nebo být členem skupiny Performance Monitor Users. Pro vzdálené test běží, účet, který kontroleru je nakonfigurovaná tak, aby spustit jako musí být členem skupiny Power Users nebo vyšší, nebo byl uživatel členem skupiny Performance Monitor Users.

## <a name="setting-the-logging-level-on-a-test-controller-computer"></a>Nastavení úrovně protokolování v testovacím počítači řadiče
 Můžete řídit úroveň protokolování v testovacím počítači řadiče. To je užitečné, když se pokoušíte diagnostikovat problém při spuštění zátěžového testu v prostředí.

### <a name="to-set-the-logging-level-on-a-test-controller-computer"></a>Chcete-li nastavit úroveň protokolování v testovacím počítači řadiče

1.  Zastavte službu testovací kontroler. Na příkazovém řádku zadejte `net stop vsttcontroller`.

2.  Otevřete soubor QTController.exe.config. Tento soubor se nachází v instalačním adresáři řadiče.

3.  Upravit položku `EqtTraceLevel` přepínače v části Diagnostika systému souboru. Váš kód by měl vypadat takto:

    ```
    <system.diagnostics>
        <trace autoflush="true" indentsize="4">
            <listeners>
                <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="d:\VSTestHost.log" />
            </listeners>
        </trace>
        <switches>
            <!-- You must use integral values for "value":
                    0 = off,
                    1 = error,
                    2 = warn,
                    3 = info,
                    4 = verbose. -->
            <add name="EqtTraceLevel" value="4" />
        </switches>
    </system.diagnostics>
    ```

4.  Uložte soubor.

5.  Spusťte službu řadiče. Na příkazovém řádku zadejte `net start vsttcontroller`.

 To platí pro testovací kontroler, Služba agenta test a proces agenta test. Při diagnostice problémů, je vhodné povolit protokolování na všechny tři procesy. Postup nastavení úrovně protokolování je stejný pro všechny tři procesy, jako zadaná výše pro testovací kontroler. Nastavení úrovně protokolování pro agenta test, služby a proces agenta, použijte následující konfigurační soubory:

-   **QTController.exe.config** Conttoller služby

-   **QTAgentService.exe.config** Agent service

-   **QTDCAgent (32).exe.config** proces adaptér dat agenta pro 32bitové architektury.

-   **QTDCAgent (64).exe.config** proces adaptér dat agenta pro 64bitová architektura.

-   **QTAgent (32).exe.config** proces test Agent pro 32bitové architektury.

-   **QTAgent (64).exe.config** proces testovacího agenta pro 64bitová architektura.

## <a name="binding-a-test-controller-to-a-network-adapter"></a>Vazba testovací kontroler k síťovému adaptéru
 Při pokusu o nastavení agenta test, může dojít k následující chybě:

 **Došlo k chybě 8110. Nelze připojit k počítači zadaný kontroler nebo přístup k objektu kontroleru.**

 Tato chyba může být způsobeno instalaci řadiče test na počítači, který má více než jeden síťový adaptér.

> [!NOTE]
>  Je také možné úspěšně nainstalovat testovacích agentů a nejsou vidět tento problém, dokud pokusu o spuštění testu.

 Pokud chcete vyřešit tuto chybu, je třeba svázat testovací kontroler jeden ze síťových adaptérů. Budete muset nastavit `BindTo` vlastnost testovacího kontroléru a poté změňte agentem test agent k odkazování na testovací kontroler podle IP adresy místo podle názvu. Postup najdete v následujících postupech.

### <a name="to-obtain-the-ip-address-of-the-network-adapter"></a>Získat IP adresu síťového adaptéru

1.  Zvolte **spustit**a potom zvolte **spustit**.

     **Spustit** se zobrazí dialogové okno.

2.  Typ `cmd` a potom zvolte **OK**.

     Otevře se příkazový řádek.

3.  Typ `ipconfig /all`.

     Zobrazí se IP adresy pro síťové adaptéry. Zaznamenejte IP adresu síťového adaptéru, který chcete vytvořit vazbu na vašem řadiči.

### <a name="to-bind-a-test-controller-to-a-network-adapter"></a>Testovací kontroler vytvořit vazbu na síťový adaptér

1.  Zastavte službu testovací kontroler. Na příkazovém řádku zadejte `net stop vsttcontroller`.

2.  Otevřete soubor QTController.exe.config. Tento soubor se nachází v % ProgramFiles(x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE.

3.  Přidejte záznam pro `BindTo` vlastnost pro nastavení aplikace. Zadejte IP adresu, kterou chcete vytvořit vazbu řadiče síťového adaptéru. Váš kód by měl vypadat takto:

    ```xml
    <appSettings>
        <add key="LogSizeLimitInMegs" value="20" />
        <add key="AgentSyncTimeoutInSeconds" value="120" />
        <add key="ControllerServicePort" value="6901" />
        <add key="ControllerUsersGroup" value="TeamTestControllerUsers" />
        <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins" />
        <add key="CreateTraceListener" value="no" />
        <add key="BindTo" value="<YOUR IP ADDRESS>" />
    </appSettings>
    ```

4.  Uložte soubor.

5.  Spusťte službu testovací kontroler. Na příkazovém řádku zadejte `net start vsttcontroller`.

### <a name="to-connect-a-test-agent-to-a-bound-controller"></a>Pro připojení k řadiči vázané testovací agent

-   Spusťte znovu instalaci agenta test. Tentokrát, zadejte IP adresu pro testovací kontroler místo názvu řadiče testu.

 To platí pro testovací kontroler, Služba agenta test a proces agenta test. `BindTo` Vlastnost musí být nastavena pro každý proces, který běží na počítači, který má více než jeden síťový adaptér. Postup pro nastavení a `BindTo` vlastnost je stejný pro všechny tři procesy, jako zadaná výše pro testovací kontroler. Pokud chcete nastavit úrovně protokolování pro službu agent test a proces agenta test, použijte konfigurační soubory, které jsou uvedeny v [nastavení úrovně protokolování v počítači řadiče testování](#Logging).

## <a name="see-also"></a>Viz také

- [Testovací kontrolery a testovací agenti](../test/configure-test-agents-and-controllers-for-load-tests.md)