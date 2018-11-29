---
title: V sadě Visual Studio nastavení protokolování zátěžových testů
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging, modifying
ms.assetid: 9649226a-857d-41ef-8ec7-047b6e498033
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 867e586b5a50dee47a86d8a57a978f51ee0d0c3b
ms.sourcegitcommit: a811f6a194ccd40d844e74e618d847df87c85c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/29/2018
ms.locfileid: "52621364"
---
# <a name="modify-load-test-logging-settings"></a>Úprava nastavení protokolování zátěžového testu

Výsledek dokončeného zátěžového testu obsahuje vzorky čítače výkonu a informace o chybách pravidelně shromažďované z testovaných počítačů do protokolu. V průběhu spuštění zátěžového testu lze shromažďovat velké množství vzorků čítačů výkonu. Množství shromážděných dat o výkonu závisí na délce běhu, intervalu vzorkování, počtu testovaných počítačů a počtu shromažďovaných čítačů. U velkých zátěžových testů může množství shromážděných dat o výkonu snadno dosáhnout několika GB, proto zvažte úpravu četnosti ukládání dat do protokolu. Zobrazit [testovací kontrolery a testovací agenty](configure-test-agents-and-controllers-for-load-tests.md).

*Testovací kontrolér* zařadí za všechny vzorkovací data shromážděná zátěžového testu do protokolu databáze, když je spuštěn test. Další data, jako jsou podrobnosti časování a podrobnosti o chybě, se načtou do databáze po dokončení testu.

|Úloha|Související témata|
|-|-----------------------|
|**Uložení protokolů, pokud zátěžový test selže:** můžete určit, jestli chcete při každém selhání testu uložit protokol testu.|-   [Postupy: určení, zda jsou selhání testu ukládána do protokolů testování](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|
|**Nastavit maximální velikost souboru protokolu:** můžete upravit konfigurační soubor XML, který je přidružený k službě kontroleru testů zadat maximální velikost souboru chcete použít pro soubor protokolu.|[Postupy: určení maximální velikosti souboru protokolu](../test/how-to-specify-the-maximum-size-for-the-log-file.md)|

## <a name="see-also"></a>Viz také:

- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)