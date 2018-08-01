---
title: Protokoly ukládání zátěžového testu v sadě Visual Studio
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
ms.openlocfilehash: 3464ffc1db1a757ac20e3f77d0d901ec731a7cab
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2018
ms.locfileid: "39381931"
---
# <a name="how-to-specify-how-frequently-test-logs-are-saved-using-the-load-test-editor"></a>Postupy: určení, jak často ukládání protokolů testování pomocí editoru zátěžových testů

Po vytvoření zátěžového testu pomocí **nového Průvodce zátěžovým testem**, můžete použít **editoru zátěžového testu** změnit zatížení testuje vlastnosti pro splnění potřebám a cílům testování. Další informace najdete v tématu [návod: vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md).

> [!NOTE]
> Úplný seznam vlastností parametrů spuštění a jejich popis najdete v části [zátěžového testu spusťte nastavení](../test/load-test-run-settings-properties.md).

Můžete určit četnost, že je protokol testu uložen v rámci zátěžového testu s použitím **editoru zátěžového testu** změnit **uložit frekvenci protokolování pro dokončení testů** vlastnost **vlastnosti** okna.

## <a name="to-specify-the-frequency-for-saving-the-test-log-in-a-load-test"></a>Chcete-li určit frekvenci pro uložení protokolu testu v rámci zátěžového testu

1.  Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí strom zátěžového testu.

2.  V zátěžového testu stromu **parametrů běhu** složky, zvolte nastavení spuštění uzlu, který chcete určit, jak často uložení protokolu testu pro.

3.  Na **zobrazení** nabídce vyberte možnost **okno vlastností**.

     Tento scénář kategorie a vlastnosti jsou zobrazeny v **vlastnosti** okna.

4.  V textovém poli pro **uložit frekvenci protokolování pro dokončení testů** vlastnost, typ Číslo označující frekvenci, s jakou se zapíše protokol testu. Číslo označuje, že jedno vzdálené každý zadaný počet testů, které se uloží do protokolu testu. Například zadáte hodnotu 10 Určuje, že desetinu, dvacáté, třicetiny a tak dále, se zapíšou do protokolu testu.

    > [!NOTE]
    > Hodnota 0 pro použití **uložit frekvenci protokolování pro dokončení testů** vlastnost určuje, že se uloží protokolů testu.

5.  Po dokončení změn vlastnosti, zvolte **Uložit** na **souboru** nabídky.

     Data uložená v protokolu lze zobrazit pomocí tabulkového zobrazení v Analyzéru zátěžového testu. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="see-also"></a>Viz také:

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Návod: Vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md)
- [Postupy: určení, zda jsou selhání testu ukládána do protokolů testování](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)
- [Postupy: nastavení shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md)