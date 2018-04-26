---
title: Uložit protokol testu zatížení pro selhání při testu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, logging
ms.assetid: 08a7fe98-a7f7-4b8d-94a3-ec82b65a2aaf
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e184fbab591698404bde4593f4ad7b61fa1815ae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-if-test-failures-are-saved-to-test-logs-using-the-load-test-editor"></a>Postupy: Určení, zda mají být selhání při testu ukládána do protokolů testování, pomocí editoru zátěžových testů

Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností testu zatížení ke splnění vašich potřeb testování a cíle. V tématu [návod: vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md). Můžete zadat, pokud chcete protokol testovací uloženy v případě, test se nezdaří v zátěžovém testu změnou **uložit protokol na Test selhání** vlastnost.

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).


## <a name="to-specify-if-the-test-log-is-saved-when-a-test-fails-in-a-scenario"></a>Určení, zda bude protokol testu při selhání testu ve scénáři uložen

1.  Otevřete zátěžový test.

     Zobrazí se Editor zátěžového testu. Zobrazí se strom zátěžového testu.

2.  V zatížení testovat stromy **spustit nastavení** složky, vyberte nastavení spuštění uzlu, který chcete určit maximální počet iterací testů ve.

3.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     V okně Vlastnosti jsou zobrazeny kategorie a vlastnosti parametrů spuštění.

4.  V **uložit protokol na Test selhání** vlastnosti, vyberte buď True nebo False k určení, zda chcete uložit test protokolu v případě selhání testu ve scénáři.

     Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky.

     Data uložená v protokolu lze zobrazit pomocí tabulkového zobrazení v Analyzéru zátěžového testu. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Návod: Vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md)
- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Postupy: nastavení shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md)
- [Postupy: Zadejte, jak často ukládání protokolů testování](../test/how-to-specify-how-frequently-test-logs-are-saved.md)