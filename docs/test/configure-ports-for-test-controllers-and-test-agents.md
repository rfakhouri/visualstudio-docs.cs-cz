---
title: Konfigurace portů pro testovací Kontroléry a testovací agenty v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- firewalls, configuring for test agents
- firewalls, configuring for test controllers
- test agents, firewalls
- test controllers, firewalls
- agents, firewalls
- controllers, firewalls
ms.assetid: 211edbd7-9fe4-4251-ba85-8bec4363261b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 4067dae0d75f5fbd4e4dfb3ff7bacfc1ff269512
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="configure-ports-for-test-controllers-and-test-agents"></a>Konfigurace portů pro testovací Kontroléry a testovací agenty

Můžete změnit výchozí příchozí porty používané řadičem testu, test agent a klienta. To může být nutné v případě, že se pokoušíte použít testovací kontroler, agentem test agent nebo klienta společně s některé další software které jsou v konfliktu s nastavením portu. Chcete-li změnit porty dalším důvodem je to z důvodu omezení brány firewall mezi testovací kontroler a klientem. V takovém případě můžete ručně nakonfigurovat port, který se zohlednit povolení brány firewall tak, aby testovací kontroler poslat výsledky do klienta.

 Následující obrázek znázorňuje spojovací body mezi řadičem testu, test agent a klienta. Se popisuje, jaké porty se používají pro příchozí a odchozí připojení a také omezení zabezpečení použít na těchto portech.

 ![Testování řadiče a otestovat agenta portů a zabezpečení](../test/media/test-controller-agent-firewall.png)

## <a name="incoming-connections"></a>Příchozí připojení

Výchozí port je používán testovacího kontroleru je 6901 a agenta test výchozí port je 6910. Klient použije náhodný port ve výchozím nastavení, která se používá k přijetí výsledky testů z testovacího kontroleru. Pro všechna příchozí připojení testovací kontroler ověří volajícího a ověřuje, že patří do konkrétní skupinu zabezpečení.

- **Testovací kontroler** jsou příchozí připojení na portu TCP 6901. Pokud potřebujete, můžete nakonfigurovat příchozí port. Další informace najdete v tématu [konfigurace portů pro příchozí](#ConfigurePorts).

    Testovací kontroler musí mít možnost provádět odchozí připojení k testovací agenti a do klienta.

    > [!NOTE]
    > Testovací kontroler musí příchozí **souborů a tiskáren sdílení** připojení otevřete.

- **Testovací Agent** jsou příchozí připojení na portu TCP 6910. Pokud potřebujete, můžete nakonfigurovat příchozí port. Další informace najdete v tématu [konfigurace portů pro příchozí](#ConfigurePorts).

   Agentem test agent musí být schopna provést odchozí připojení k testovacímu kontroleru.

- **Klient** ve výchozím nastavení, je použít náhodný port TCP pro příchozí připojení. Pokud potřebujete, můžete nakonfigurovat příchozí port. Další informace najdete v tématu [konfigurace portů pro příchozí](#ConfigurePorts).

   Pokud testovací kontroler, pokusí se připojit k čas klienta první, může získat brány firewall oznámení.

   V systému Windows Server 2008 jsou ve výchozím nastavení zakázané oznámení brány firewall a je třeba ručně přidat výjimky brány Firewall pro klienta programy (devenv.exe, mstest.exe, mlm.exe) tak, aby může zpracovávat příchozí připojení.

## <a name="outgoing-connections"></a>Odchozí připojení

Náhodné porty TCP se používají pro všechny odchozí připojení.

- **Testovací kontroler** testovací kontroler musí mít možnost provádět odchozí připojení s agenty a do klienta.

- **Testovací Agent** agentem test agent musí být schopna provést odchozí připojení k řadiči.

- **Klient** klient musí mít možnost provádět odchozí připojení k řadiči.

## <a name="configure-the-incoming-ports"></a>Konfigurace portů pro příchozí

Postupujte podle těchto pokynů ke konfiguraci portů pro testovací kontroler a testovací agenti.

- **Služba řadiče** změnit hodnotu portu úpravou souboru % ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTCcontroller.exe.config:

    ```xml
    <appSettings>
      <add key="ControllerServicePort" value="6901"/>
    </appSettings>
    ```

- **Služba agenta** změnit port úpravou souboru % ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTAgentService.exe.config:

    ```xml
    <appSettings>
      <add key="AgentServicePort" value="6910"/>
    </appSettings>
    ```

- **Klient** pomocí Editoru registru přidejte následující hodnoty registru (DWORD). Klient bude pro příjem dat z testovacího kontroleru, použijte jednu z porty z zadaný rozsah:

     HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\VisualStudio\12.0\EnterpriseTools\QualityTools\ListenPortRange\PortRangeStart

     HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\VisualStudio\12.0\EnterpriseTools\QualityTools\ListenPortRange\PortRangeEnd

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)