---
title: Konfigurace testovacích agentů a testovací kontrolery pro zátěžové testy v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, test agents and controllers
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 388be0aa6b1d9bad7ec90620bd025530b3d0e00d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="configure-test-agents-and-test-controllers-for-running-load-tests"></a>Konfigurace testovacích agentů a testovací kontrolery pro spouštění zátěžových testů

Visual Studio můžete vygenerovat simulované zatížení pro vaši aplikaci pomocí fyzických nebo virtuálních počítačů. Tyto počítače musí být nastavený jako jeden testovacího kontroléru a testovacích agentů pro jeden nebo více. Testovací kontrolery a testovací agenty můžete použít ke generování zatížení více než jeden počítač můžete vygenerovat samostatně.

> [!NOTE]
> Cloudové zátěžové testování můžete použít také k poskytování virtuálních počítačů, které generují zatížení mnoha uživateli přístup k webu ve stejnou dobu. Další informace o cloudové zátěžové testování v [spouštění zátěžových testů pomocí služby VSTS](/vsts/load-test/get-started-simple-cloud-load-test).

## <a name="load-simulation-architecture"></a>Architektura simulace zátěže

Architektura simulace zátěže se skládá z klientské aplikace Visual Studio, testovacího kontroléru a testovacích agentů.

-   Klient se používá pro vývoj a spouštění testů a zobrazování jejich výsledků.

-   Testovací kontrolér slouží ke správě testovacích agentů a shromažďování výsledků testu.

-   Testovací agenty se používají ke spouštění testů a shromažďování dat včetně systémových informací a dat profilování ASP.NET definovaných v nastavení testu.

Tato architektura přináší následující výhody:

-   Možnost škálovat generování zátěže přidáváním dalších testovacích agentů k testovacímu kontroléru.

-   Pružnost při instalaci softwaru klientu, testovacího kontroléru a testovacího agentu na stejném počítači i různých počítačích. Příklad:

     **Místní konfigurace:**

    -   Počítač 1: Visual Studio, kontrolér, agent.

     ![Místní počítače pomocí řadiče a agent](./media/load-test-configa.png)

     **Typické konfigurace vzdáleného:**

    -   Počítač 1 a 2: Visual Studio (více testerů může používat stejný kontrolér).

    -   Počítač 3: Kontrolér (může mít nainstalovány také agenty).

    -   Machine4-n: agenta a přidružených ke kontroleru na POČÍTAČ3 všechny agenty.

     ![Vzdálené počítače pomocí kontroléru a agentů](./media/load-test-configb.png)

Přestože testovací kontrolér obvykle spravuje několik testovacích agentů, jeden agent může být přidružen pouze k jednomu kontroléru. Každý testovací agent může být sdílen týmem vývojářů. Tato architektura umožňuje snadno zvýšit počet testovacích agentů a generovat tak větší zátěž.

## <a name="test-agent-and-test-controller-interaction"></a>Interakce testovacího agentu a testovacího kontroléru

Testovací kontrolér spravuje sadu testovacích agentů pro spouštění testů. Testovací kontroler komunikuje s testovací agenty testy spuštění, zastavení testů, sledovat stav agenta test a výsledky testu shromažďování.

### <a name="test-controller"></a>Testovací kontroler

Testovací kontrolér poskytuje obecnou architekturu pro spouštění testů a zahrnuje speciální funkce pro spouštění zátěžových testů. Testovací kontrolér odesílá zátěžový test všem testovacím agentům a čeká, dokud není test inicializován všemi agenty. Jsou-li všichni testovací agenti připraveni, řadič testů jim odešle zprávu, aby zahájili test.

### <a name="test-agent"></a>Test Agent

Testovací agent je spouštěn jako služba, která naslouchá požadavkům testovacího kontroléru na spuštění nového testu. Žádost o přijetí agentem test agent služby agenta test spustí proces, na kterém chcete spustit testy. Každý testovací agent spouští stejný zátěžový test.

 Testovacím agentům je správcem přiřazována váha a zátěž je přerozdělena dle váhy jednotlivých agentů. Pokud má například testovací agent 1 váhu 30 a testovací agent 2 váhu 70, přičemž je zátěž nastavena na 1000 uživatelů, testovací agent 1 simuluje 300 virtuálních uživatelů, zatímco testovací agent 2 jich simuluje 700. V tématu [Správa testovacích Kontrolérů a testovacích agentů v sadě Visual Studio](../test/manage-test-controllers-and-test-agents.md).

 Testovací agent vezme jako vstupní sadu testů a sadu parametrů simulace. Klíče koncept je nezávislé na počítači, kde jste spustit testy.

## <a name="test-controller-and-test-agent-connection-points"></a>Spojovací body testovacího kontroléru a testovacího agentu

Následující obrázek znázorňuje spojovací body mezi testovacím kontrolérem, testovacím agentem a klientem. Se popisuje, jaké porty se používají pro příchozí a odchozí připojení a také omezení zabezpečení použít na těchto portech.

 ![Testování řadiče a otestovat agenta portů a zabezpečení](./media/test-controller-agent-firewall.png)

 Další informace najdete v části [konfigurace portů pro testovací Kontroléry a testovací agenty](../test/configure-ports-for-test-controllers-and-test-agents.md).

## <a name="test-controller-and-agent-installation-information"></a>Informace o instalaci testovacího kontroléru a agentu

Důležité informace o požadavcích na hardware a software pro testovacích kontrolérů a testovacích agentů najdete v tématu postupy pro spuštění instalace a konfigurace prostředí pro optimální výkon, [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

## <a name="using-the-test-controller-and-test-agent-with-unit-tests"></a>Použití testovacího kontroléru a testovacího agentu při testování částí

Po instalaci testovacího kontroléru a jednoho nebo více agentů lze v nastavení zátěžových testů určit, zda má být u kontroléru používáno vzdálené spuštění. Dále lze v nastavení testu určit datové a diagnostické adaptéry, které mají být použity spolu s rolí přidruženou k agentům.

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)