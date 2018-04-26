---
title: Zadejte počtu testovacích iterací v parametrech běhu testu zatížení v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, properties
- load tests, run settings
ms.assetid: 45a625db-b3e7-4d64-beda-b9a76248096d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: ec11561a3ebe084517d1a30266f9caa6491544a7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-the-number-of-test-iterations-in-a-load-test-run-setting"></a>Postupy: Určení počtu testovacích iterací v parametrech běhu zátěžového testu

Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností scénáře pro splnění vašich potřeb testování a cíle. Další informace najdete v tématu [návod: vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md).

Pomocí **editoru zátěžových testů**, můžete upravit **testovacích iterací** vlastnost hodnoty parametrů běhu v okně Vlastnosti. **Testování iterací** vlastnost určuje počet iterací ke spuštění na všechny webové výkonu a jednotka testy ve všech scénářích v zátěžovému testu pomocí **načíst Editor testů**.

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).


## <a name="to-specify-the-number-of-test-iterations-in-a-run-setting"></a>K určení počtu testovacích iterací v parametrech běhu

1.  Otevřete zátěžový test.

     **Načíst Editor testů** se zobrazí a zobrazí stromu testu zatížení.

2.  V zatížení otestovat ve stromu **spustit nastavení** složky, vyberte spuštění nastavení.

3.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno** zobrazíte zatížení spustit kategorií a vlastností nastavení.

4.  Nastavte **použití testovacích iterací** vlastnost **True**.

5.  V **testování iterací** vlastnost, zadejte číslo určující počet iterací testů, pokud chcete spustit během zátěžového testu.

6.  Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky. Potom můžete spustit vaší zátěžového testu pomocí nové **testování iterací** hodnotu.

## <a name="see-also"></a>Viz také

- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)