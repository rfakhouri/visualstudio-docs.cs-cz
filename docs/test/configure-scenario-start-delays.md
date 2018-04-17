---
title: Konfigurace zpoždění spuštění scénáře pro testování v sadě Visual Studio zatížení | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios, start delays
ms.assetid: 2f634fba-8dfa-4c7a-a8b9-be867b78d16a
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: f39f19e0c09da69ff82718f9c0f6efd8d05a77de
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="configure-scenario-start-delays-in-load-tests"></a>Konfigurace zpoždění pro spuštění scénáře v zátěžových testech

Zadejte zpoždění před zahájením scénáři v zátěžovém testu pomocí editoru načíst testování a v okně Vlastnosti.

Například můžete chtít použít **čas spuštění zpoždění** vlastnost Pokud budete potřebovat jeden scénář zahájíte vytváření položek, které využívá jiný scénář. Může pozdržet náročné scénář povolit vytváření scénář k naplnění některá data.

Dalším příkladem je, že můžete mít jeden scénář, který se spustí pouze v určitém čase dne. Ano budete chtít zpoždění spuštění scénář k simulaci to.

## <a name="specifying-the-delay-start-time-of-a-scenario"></a>Určení zpoždění čas spuštění scénáře

Zpoždění před zahájením scénáři můžete zadat v zátěžovém testu pomocí editoru načíst testování změnit **čas spuštění zpoždění** vlastnost v okně Vlastnosti.

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [načíst vlastnosti scénář otestovat](../test/load-test-scenario-properties.md).

 Příkladem instanci, pokud chcete použít **čas spuštění zpoždění** vlastnost je, když potřebujete jeden scénář zahájíte vytváření položek, které využívá jiný scénář. Může pozdržet náročné scénář povolit vytváření scénář k naplnění některá data.

 Dalším příkladem je, že můžete mít jeden scénář, který se spustí pouze v průběhu dne. Chcete proto zpoždění spuštění scénář k simulaci to.

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

### <a name="to-specify-the-delay-start-time-for-a-scenario"></a>Chcete-li určit zpoždění počáteční čas pro scénář

1. Otevřete zátěžový test.

     Zobrazí se Editor zátěžového testu. Zobrazí se strom zátěžového testu.

2. V zatížení testovat stromy **scénáře** složky, vyberte uzel scénář, pro který chcete zadat čas spuštění zpoždění.

3. Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Kategorií a vlastností scénáře jsou zobrazeny v okně Vlastnosti.

4. Do textového pole pro **čas spuštění zpoždění** vlastnosti, typ čas hodnotu, která určuje dobu čekání po zátěžový test spustí před zahájením tohoto scénáře při spuštění zátěžového testu.

    > [!NOTE]
    > Pokud hodnota **zakázat během zahřívání** vlastnost pro tento scénář je nastavena na **True**, pak se **čas spuštění zpoždění** hodnotu vlastnosti doby budou použity po warm-up období. Můžete řídit, které scénáře jsou součástí warm-up pomocí **zakázat během zahřívání** vlastnost scénář.

5. Po provedení změny vlastnosti, vyberte **Uložit** na **souboru** nabídky. Když pak spustíte zátěžový test pomocí nové **čas spuštění zpoždění** hodnotu.

## <a name="enabling-and-disabling-whether-a-scenario-runs-during-the-warm-up-period"></a>Povolení a zakázání zda scénáři spouští během období warm-up 1.0

**Zakázat během zahřívání** je nastavena pomocí vlastnosti okna. Úpravy vlastnosti scénáře zátěžového testu nastavena pomocí editoru načíst otestovat.

 **Zakázat během zahřívání** vlastnost se používá k označení, zda by měl tento scénář spustit nebo nepoběží během období warm-up, který je uveden v **čas spuštění zpoždění** vlastnost. Další informace najdete v tématu předchozí postup [zadat čas spuštění zpoždění scénáře](../test/configure-scenario-start-delays.md#ConfiguringScenarioStartDelayHowTo).

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

### <a name="to-enable-or-disable-the-warm-up-period-for-a-scenario"></a>K povolení nebo zakázání období warm-up pro scénáře

1. Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2. V zatížení testovat stromy **scénáře** složky, vyberte uzlu scénář, který chcete určit agenty používat.

3. Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Tento scénář kategorií a vlastností se zobrazí v okně Vlastnosti.

     V **zakázat během zahřívání** vlastnosti, vyberte buď **True** nebo **False.**

4. Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky. Potom můžete spustit vaší zátěžového testu pomocí nové **zakázat během zahřívání** hodnotu.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Konfigurace testovacích agentů a testovací kontrolery pro zátěžové testy](../test/configure-test-agents-and-controllers-for-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)