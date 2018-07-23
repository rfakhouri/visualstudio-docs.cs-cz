---
title: Přidat pravidlo mezní hodnoty pro zátěžové testování v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, monitoring
- load tests, thresholds
- load tests, analyzing
- thresholds in load tests
ms.assetid: 3d8fac8f-426f-4155-9ced-f7cd4c79792c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: f68ab9b183119c18bed51bb7faaa86993d7f34ce
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179876"
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>Postupy: Přidání mezního pravidla pomocí editoru zátěžových testů

Mezní pravidla v zátěžových testech porovnávají hodnotu čítače výkonu s konstantní hodnotou nebo jinou hodnotou čítače výkonu.

## <a name="to-add-a-threshold-rule"></a>Chcete-li přidat mezní pravidlo:

1.  Otevřete zátěžový test.

2.  V editoru zátěžového testu rozbalte **sady čítačů** uzlu.

3.  Rozbalte některou **kategorie čítačů** v jedné ze sad čítačů. Například můžete vybrat **loadtest: Scenario**. Rozbalte uzel.

4.  Klikněte pravým tlačítkem z čítačů, například **uživatelské zatížení**v části **loadtest: Scenario**. Vyberte **přidat pravidlo mezní hodnoty**.

     **Přidat pravidlo mezní hodnoty** se zobrazí dialogové okno.

5.  Můžete vybrat ze dvou typů pravidel: **konstanta porovnání** a **čítač porovnání**. Vyberte požadovaný typ a nastavte hodnoty.

    > [!NOTE]
    > Nastavte **upozornění, pokud přesáhne** vlastnost **True** k označení, že překročení mezní hodnoty je nějaký problém nebo **False** označuje, že snížení pod mezní hodnotu k problému.

## <a name="see-also"></a>Viz také:

- [Analýza překročení mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
