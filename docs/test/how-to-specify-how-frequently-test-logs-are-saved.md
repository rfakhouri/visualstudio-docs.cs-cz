---
title: Protokoly ukládání zátěžový test v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, logging
ms.assetid: 9ac88d8a-4777-462c-aa0e-244dadb2cfd1
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 4114a938f643cee629311a72aec72f94cfcd2fc4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-how-frequently-test-logs-are-saved-using-the-load-test-editor"></a>Postupy: Určení frekvence ukládání protokolů testování pomocí editoru zátěžových testů

Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** změnit zatížení testy vlastnosti pro splnění vašich potřeb testování a cíle. Další informace najdete v tématu [návod: vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md).

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).

Můžete zadat frekvenci, testovací protokol je uložen v zátěžovém testu pomocí editoru načíst testování změnit **uložit četnost protokolu pro dokončení testů** vlastnost v okně Vlastnosti.

## <a name="to-specify-the-frequency-for-saving-the-test-log-in-a-load-test"></a>K určení frekvence ukládání protokolů test v zátěžovém testu

1.  Otevřete zátěžový test.

     Zobrazí se Editor zátěžového testu. Zobrazuje stromu testu zatížení.

2.  V zatížení testovat stromy **spustit nastavení** složky, vyberte nastavení spuštění uzlu, který chcete určit, jak často, že je protokol testovací uložit.

3.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Tento scénář kategorií a vlastností se zobrazí v okně Vlastnosti.

4.  Do textového pole pro **uložit četnost protokolu pro dokončení testů** vlastnost, zadejte číslo udávající frekvenci, kdy se zapíše protokol testu. Číslo označuje, že jeden z každé zadané číslo testů budou uloženy do protokolu testovací. Zadat hodnotu deset například určuje, že desetinu, dvacetinu, třicetiny a tak dále se zapíšou do protokolu testu.

    > [!NOTE]
    > Hodnota 0 pro použití **uložit četnost protokolu pro dokončení testů** vlastnost určuje, že jsou uloženy žádné protokolů testování.

5.  Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky.

     Data uložená v protokolu lze zobrazit pomocí tabulkového zobrazení v Analyzéru zátěžového testu. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Návod: Vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md)
- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Postupy: určení, zda jsou selhání při testu ukládána do protokolů testování](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)
- [Postupy: nastavení shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md)