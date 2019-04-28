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
ms.openlocfilehash: 2a5865eba5ec6971a35104af3ccd090ee6b06410
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63002294"
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>Postupy: Přidání mezního pravidla pomocí editoru zátěžových testů

Mezní pravidla v zátěžových testech porovnávají hodnotu čítače výkonu s konstantní hodnotou nebo jinou hodnotou čítače výkonu.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-add-a-threshold-rule"></a>Chcete-li přidat mezní pravidlo:

1. Otevřete zátěžový test.

2. V editoru zátěžového testu rozbalte **sady čítačů** uzlu.

3. Rozbalte některou **kategorie čítačů** v jedné ze sad čítačů. Například můžete vybrat **loadtest: Scenario**. Rozbalte uzel.

4. Klikněte pravým tlačítkem z čítačů, například **uživatelské zatížení**v části **loadtest: Scenario**. Vyberte **přidat pravidlo mezní hodnoty**.

     **Přidat pravidlo mezní hodnoty** se zobrazí dialogové okno.

5. Můžete vybrat ze dvou typů pravidel: **Porovnat konstanty** a **porovnání čítač**. Vyberte požadovaný typ a nastavte hodnoty.

    > [!NOTE]
    > Nastavte **upozornění, pokud přesáhne** vlastnost **True** k označení, že překročení mezní hodnoty je nějaký problém nebo **False** označuje, že snížení pod mezní hodnotu k problému.

## <a name="see-also"></a>Viz také:

- [Analýza překročení mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
