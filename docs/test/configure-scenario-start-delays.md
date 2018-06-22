---
title: Konfigurace zpoždění spuštění scénář pro zátěžové testování
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios, start delays
ms.assetid: 2f634fba-8dfa-4c7a-a8b9-be867b78d16a
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 30a19e786894a9722e6843a5c1c69cdf1f038e58
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36296379"
---
# <a name="configure-scenario-start-delays-in-load-tests"></a>Konfigurace zpoždění pro spuštění scénáře v zátěžových testech

Zadejte zpoždění před zahájením scénáři v zátěžovém testu pomocí editoru načíst testování a **vlastnosti** okno.

Například můžete chtít použít **čas spuštění zpoždění** vlastnost Pokud budete potřebovat jeden scénář zahájíte vytváření položek, které využívá jiný scénář. Může pozdržet náročné scénář povolit vytváření scénář k naplnění některá data.

Dalším příkladem je, že můžete mít jeden scénář, který se spustí pouze v určitém čase dne. Ano budete chtít zpoždění spuštění scénář k simulaci to.

## <a name="specify-the-delay-start-time-of-a-scenario"></a>Zadejte počáteční čas zpoždění scénáře

Zpoždění před zahájením scénáři můžete zadat v zátěžovém testu pomocí editoru načíst testování změnit **čas spuštění zpoždění** vlastnost **vlastnosti** okno.

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

 Příkladem instanci, pokud chcete použít **čas spuštění zpoždění** vlastnost je, když potřebujete jeden scénář zahájíte vytváření položek, které využívá jiný scénář. Může pozdržet náročné scénář povolit vytváření scénář k naplnění některá data.

 Dalším příkladem je, že můžete mít jeden scénář, který se spustí pouze v průběhu dne. Chcete proto zpoždění spuštění scénář k simulaci to.

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

### <a name="to-specify-the-delay-start-time-for-a-scenario"></a>Chcete-li určit zpoždění počáteční čas pro scénář

1. Otevřete zátěžový test.

     Zobrazí se Editor zátěžového testu. Zobrazí se strom zátěžového testu.

2. V zatížení testovat stromy **scénáře** složky, vyberte uzel scénář, pro který chcete zadat čas spuštění zpoždění.

3. Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Kategorií a vlastností tohoto scénáře se zobrazují v **vlastnosti** okno.

4. Do textového pole pro **čas spuštění zpoždění** vlastnosti, typ čas hodnotu, která určuje dobu čekání po zátěžový test spustí před zahájením tohoto scénáře při spuštění zátěžového testu.

    > [!NOTE]
    > Pokud hodnota **zakázat během zahřívání** vlastnost pro tento scénář je nastavena na **True**, pak se **čas spuštění zpoždění** hodnotu vlastnosti doby budou použity po warm-up období. Můžete řídit, které scénáře jsou součástí warm-up pomocí **zakázat během zahřívání** vlastnost scénář.

5. Po provedení změny vlastnosti, vyberte **Uložit** na **souboru** nabídky. Když pak spustíte zátěžový test pomocí nové **čas spuštění zpoždění** hodnotu.

## <a name="enable-and-disable-whether-a-scenario-runs-during-the-warm-up-period"></a>Povolit a zakázat, zda scénáři spouští během období warm-up 1.0

**Zakázat během zahřívání** je nastavena pomocí **vlastnosti** okno. Úpravy vlastnosti scénáře zátěžového testu nastavena pomocí editoru načíst otestovat.

 **Zakázat během zahřívání** vlastnost se používá k označení, zda by měl tento scénář spustit nebo nepoběží během období warm-up, který je uveden v **čas spuštění zpoždění** vlastnost. Další informace najdete v tématu předchozí postup [zadejte zpoždění spuštění scénáře](#specify-the-delay-start-time-of-a-scenario).

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

### <a name="to-enable-or-disable-the-warm-up-period-for-a-scenario"></a>K povolení nebo zakázání období warm-up pro scénáře

1. Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2. V zatížení testovat stromy **scénáře** složky, vyberte uzel scénář, který chcete změnit chování zahřívání.

3. Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Tento scénář kategorií a vlastností se zobrazují v **vlastnosti** okno.

     V **zakázat během zahřívání** vlastnosti, vyberte buď **True** nebo **False.**

4. Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky. Potom můžete spustit vaší zátěžového testu pomocí nové **zakázat během zahřívání** hodnotu.

## <a name="see-also"></a>Viz také:

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Konfigurace testovacích agentů a testovací kontrolery pro zátěžové testy](../test/configure-test-agents-and-controllers-for-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)