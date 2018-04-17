---
title: 'Postupy: shromažďování dat čítačů procesoru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.cpucounters
helpviewer_keywords:
- profiling tools, using portable CPU counters
- performance tools, portable CPU counters
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a47f116dadff8a56b1aafc94b4bbfa5e22ff7a2c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-collect-cpu-counter-data"></a>Postupy: Shromažďování dat čítačů procesoru

Čítač Procesor událostí se používá ke shromažďování dat výkonu hardwaru. Toto téma ukazuje, jak shromažďování dat čítačů událostí při použití metoda profilování instrumentace.

Provedou se dva typy událostí čítače procesoru:

- Přenosné události - procesoru události, které se můžou shromažďovat, bez ohledu na určitém procesoru.

- Platforma události - procesoru události, které jsou doplněná na určitém procesoru.

 Přenosné události zahrnují obecné události, jako je vyřazeno pokyny a bez cykly zastavit, procesoru vyrovnávací paměti události, větvení události a události L2 mezipaměti. Čítače událostí k dispozici platforma jsou určeny výrobce procesoru.

 Kategorie události lze sdílet mezi přenositelností a platforma čítače. Například následující kategorie dat jsou často společné pro oba typy:

- Události paměti.

- Front-endu události.

- Větev událostí.

 Můžete shromáždit data čítače výkonu v profileru dvěma způsoby:

- Shromažďování dat z jedné nebo více čítačů, když profilu pomocí instrumentace.

- Zadejte čítač událostí jako interval vzorkování při profilu pomocí vzorkování. Další informace najdete v tématu [postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md).

## <a name="to-collect-cpu-performance-counter-data-when-you-profile-by-instrumentation"></a>Shromažďování dat čítačů výkonu procesoru, je-li profil pomocí instrumentace

1. V relaci výkonu **stránky vlastností**, klikněte na tlačítko **čítače CPU.**

2. Vyberte **shromažďování čítače CPU** zaškrtávací políčko.

3. Rozbalte **čítače výkonu k dispozici** stromu vyhledejte ukázkové události, které chcete shromažďovat.

4. Pro každou jednotlivou událost, který chcete shromáždit, vyberte událost a potom klikněte na tlačítko se šipkou doprava přidejte události **vybrané čítače** seznamu.

    > [!NOTE]
    > **K dispozici čítače** je povoleno pouze v případě, že jste vybrali **čítače CPU shromažďovat** zaškrtávací políčko.

## <a name="see-also"></a>Viz také

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)  
[Využití procesoru a čítačů systému Windows](../profiling/cpu-and-windows-counters.md)  
[Postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md)