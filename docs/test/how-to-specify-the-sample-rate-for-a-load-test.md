---
title: 'Postupy: určení vzorkovací frekvence pro spuštění zátěžového testu v sadě Visual Studio'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings
ms.assetid: 51cbe7d6-5dfd-4842-bca3-f7f8a665dc84
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 18fa71396caa0c164ef7f37183cda28c701cf4f8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970047"
---
# <a name="how-to-specify-the-sample-rate-for-a-load-test-run-setting"></a>Postupy: Určení vzorkovací frekvence v parametrech běhu zátěžového testu

Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností pro splnění vašich potřeb testování a cíle.

Pomocí **editoru zátěžových testů**, můžete upravit nastavení spuštění **vzorkovací frekvence** hodnotu vlastnosti v **vlastnosti** okno. Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).

Vyberte hodnotu odpovídající **vzorkovací frekvence** vlastnost pro zátěžový test, spusťte nastavení podle délka zátěžový test. Menší vzorkovací frekvence, jako je například na výchozí hodnotu pět sekund, vyžaduje více místa v databázi výsledky testu zatížení. Pro delší zátěžové testy zvýšení vzorkovací frekvence sníží množství dat, které shromažďujete. Další informace najdete v tématu [postupy: určení vzorkovací frekvence pro spuštění zátěžového testu](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Zde jsou uvedeny pokyny pro vzorkovací frekvence:

|Doba trvání testu zatížení|Doporučená vzorkovací frekvence|
|------------------------|-----------------------------|
|\< 1 hodina|5 sekund|
|1 - 8 hodin|15 sekund|
|8 – 24 hodin|30 sekund|
|> 24 hodin|60 sekund|

## <a name="to-specify-performance-counter-sampling-rate-in-a-run-setting"></a>Chcete-li určit míry vzorkování čítače výkonu v parametrech běhu

1.  Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2.  V zatížení otestovat ve stromu **spustit nastavení** složky, vyberte spuštění nastavení, které chcete určit vzorkovací frekvence.

3.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Zatížení spustit kategorií a vlastností nastavení se zobrazí v okně Vlastnosti.

4.  V **vzorkovací frekvence** vlastnost, zadejte čas hodnotu, která určuje četnost, kdy bude zátěžového testu shromažďování dat čítačů výkonu.

5.  Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky. Potom můžete spustit vaší zátěžového testu pomocí nové **vzorkovací frekvence** hodnotu.

## <a name="see-also"></a>Viz také

- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)