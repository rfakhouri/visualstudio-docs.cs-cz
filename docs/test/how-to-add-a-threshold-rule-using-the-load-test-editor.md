---
title: Přidat pravidlo mezní hodnoty pro zátěžové testování
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
manager: jillfra
ms.prod: visual-studio-dev15
ms.openlocfilehash: e06ed07ba37b6f9c6442c69edab86aaf0f10e9de
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971098"
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>Postupy: Přidání mezního pravidla pomocí editoru zátěžových testů

Mezní pravidla v zátěžových testech porovnávají hodnotu čítače výkonu s konstantní hodnotou nebo jinou hodnotou čítače výkonu.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-add-a-threshold-rule"></a>Chcete-li přidat mezní pravidlo:

1.  Otevřete zátěžový test.

2.  V editoru zátěžového testu rozbalte **sady čítačů** uzlu.

3.  Rozbalte některou **kategorie čítačů** v jedné ze sad čítačů. Například můžete vybrat **loadtest: Scenario**. Rozbalte uzel.

4.  Klikněte pravým tlačítkem z čítačů, například **uživatelské zatížení**v části **loadtest: Scenario**. Vyberte **přidat pravidlo mezní hodnoty**.

     **Přidat pravidlo mezní hodnoty** se zobrazí dialogové okno.

5.  Můžete vybrat ze dvou typů pravidel: **Porovnat konstanty** a **porovnání čítač**. Vyberte požadovaný typ a nastavte hodnoty.

    > [!NOTE]
    > Nastavte **upozornění, pokud přesáhne** vlastnost **True** k označení, že překročení mezní hodnoty je nějaký problém nebo **False** označuje, že snížení pod mezní hodnotu k problému.

## <a name="see-also"></a>Viz také:

- [Analýza překročení mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
