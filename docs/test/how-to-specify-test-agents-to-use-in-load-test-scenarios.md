---
title: Zadejte testovacích agentů pro použití v zatížení scénáře otestovat v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- test agents, load tests
- load tests, scenarios
- load tests, specifying for load tests
- tests agents, load tests, specifying
- load tests, test agents
ms.assetid: e86806dd-5897-4e4c-bfd4-8d687fb72a6e
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: dd6ca0c9b92f8eaa27c2a8726cc9d2cea49636b2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-test-agents-to-use-in-load-test-scenarios"></a>Postupy: Určení testovacích agentů, kteří mají být použiti ve scénářích zátěžových testů

Jakmile vytvoříte zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností scénáře pro splnění vašich potřeb testování a cíle.

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [načíst vlastnosti scénář otestovat](../test/load-test-scenario-properties.md).

Agenti nejsou zadány pomocí editoru zátěžových testů změnit **agentů pro použití** vlastnost v okně Vlastnosti.

Můžete zadat agentů, které chcete, aby váš scénář má použít, pokud používáte řadiče a testovací agenty ke spuštění zatížení vzdáleně. Může být například potřeba určit konkrétní sadu agentů, aby byla při analýze trendů výkonu zachována konzistence. Navíc agenti mohou být geograficky distribuovány, tak, aby spřažení existuje mezi skripty, které mohou být spuštěny a kde se nachází agent.

> [!TIP]
> Místo fyzicky uvedení agenta vzdálené sítě, Další možností je použít emulace sítě k emulaci pomalé síti. Další informace najdete v tématu [určení typů virtuálních síťových](../test/specify-virtual-network-types-in-a-load-test-scenario.md) a [určení typů virtuálních síťových](../test/specify-virtual-network-types-in-a-load-test-scenario.md).

Další informace najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

Dalším důvodem je, že některé, ale ne všechny agenty může mít na nich být nainstalovaný software, který je vyžadován pro konkrétní scénář.

Můžete řídit výběr agenta pro danou test spusťte pomocí rolí v nastavení testu. Další informace najdete v tématu [shromažďovat diagnostické informace využitím testovacích nastavení](../test/collect-diagnostic-information-using-test-settings.md).

Pokud testovacího počítače agenta má více než 75 procent využití procesoru nebo menší než 10 procent dostupné fyzické paměti, přidejte do vaší zátěžový test, abyste měli jistotu, že se počítač agenta nestane kritická místa v zátěžovém testu více agentů.

## <a name="to-specify-the-agents-to-use-for-a-scenario"></a>Chcete-li určit agenty používat pro scénáře

1.  Otevřete zátěžový test.

     Zobrazí se Editor zátěžového testu. Zobrazí se strom zátěžového testu.

2.  V zatížení testovat stromy **scénáře** složky, vyberte uzel scénář, pro který chcete určit agenty používat.

3.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Kategorií a vlastností scénáře jsou zobrazeny v okně Vlastnosti.

4.  Do textového pole pro **agentů pro použití** vlastnost, zadejte seznam agentů, na kterých může spustit tento scénář.

     Agenti musí být oddělené čárkami, například "**Agent1, Agent2, Agent3**". Je-li tato vlastnost ponechána prázdná, scénář bude používat všechny dostupné agenty.

    > [!NOTE]
    > **Agentů pro použití** vlastnost se ignoruje při místním spuštění. Pro vzdálené spuštění, pokud není k dispozici z agentů, zadaný v **agentů pro použití** neexistuje, testy v tomto scénáři se nespustí.

5.  Po provedení změny vlastnosti, vyberte **Uložit** na **souboru** nabídky. Když pak spustíte zátěžový test pomocí nové **agentů pro použití** hodnotu.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Návod: Vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md)
- [Kontrolery testů a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)