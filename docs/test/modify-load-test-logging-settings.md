---
title: Načtení nastavení protokolování testů v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging, modifying
ms.assetid: 9649226a-857d-41ef-8ec7-047b6e498033
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 7f33d25f471e683a50fd37eab669917a319cf60a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="modify-load-test-logging-settings"></a>Úprava nastavení protokolování zátěžových testů

Výsledek dokončeného zátěžového testu obsahuje vzorky čítače výkonu a informace o chybách pravidelně shromažďované z testovaných počítačů do protokolu. Během spuštění zátěžového testu se můžou shromažďovat velký počet vzorků. Množství shromážděných dat o výkonu závisí na délce běhu, intervalu vzorkování, počtu testovaných počítačů a počtu shromažďovaných čítačů. U velkých zátěžových testů může množství shromážděných dat o výkonu snadno dosáhnout několika GB, proto zvažte úpravu četnosti ukládání dat do protokolu. V tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

*Testovací kontroler* zařadí do fronty všechny shromážděné zatížení testovací ukázková data do protokolu databáze je spuštěn test. Další data, jako je například časování podrobnosti a podrobnosti o chybě, je po dokončení testu načten do databáze.

|Úloha|Související témata|
|----------|-----------------------|
|**Zadejte, jak často se uložit protokoly během spuštění zátěžového testu:** můžete určit, jak často se mají uložit při spuštění zátěžového testu test protokolu.|-   [Postupy: Zadejte, jak často ukládání protokolů testování](../test/how-to-specify-how-frequently-test-logs-are-saved.md)|
|**Uložte protokoly, pokud selže zátěžový test:** můžete zadat, pokud chcete uložit protokol testovací vždy, když zátěžový test se nezdaří.|-   [Postupy: určení, zda jsou selhání při testu ukládána do protokolů testování](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|
|**Nastavit maximální velikost souboru protokolu:** můžete upravit konfigurační soubor XML, který je přidružen služba řadiče testovací zadat maximální velikost souboru chcete použít pro soubor protokolu.|[Postupy: určení maximální velikosti souboru protokolu](../test/how-to-specify-the-maximum-size-for-the-log-file.md)|

## <a name="related-tasks"></a>Související úlohy

Je související vlastnost **podrobností časování** úložiště. Další informace najdete v tématu [postupy: Konfigurace shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md).

## <a name="see-also"></a>Viz také

- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)