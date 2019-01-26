---
title: 'DA0008: Shromážděno málo vzorků | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: baf973837a687bb102dd857adf97caf0e1b8e5ab
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55001771"
---
# <a name="da0008-few-samples-collected"></a>DA0008: Shromážděno málo ukázek

|||  
|-|-|  
|Id pravidla|DA0008|  
|Kategorie|Použití nástroje pro profilaci|  
|Metoda profilace|Vzorkování|  
|Zpráva|Nebyly shromážděny vzorky jenom pár. Zvažte delší spuštění nebo rychlejší vzorkovací frekvenci pro více významné výsledky.|  
|Typ pravidla|Informace o|  

## <a name="cause"></a>Příčina  
 Při spuštění profilace nebyly shromážděny vzorky jenom pár.  

## <a name="rule-description"></a>Popis pravidla  
 Při použití metody vzorkování mají shromažďovat statisticky významná počet vzorků, abyste měli jistotu, že data představují chování skutečný program. Chcete-li minimalizovat chyby vzorkování, doporučujeme shromáždit alespoň 1000 vzorky chování při spuštění programu instrukce. Pokud shromažďujete není dostatek ukázky, které můžete omyl, při analýze dat profilace.  

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vezměte v úvahu profilování už spuštění aplikace nebo rychlejší vzorkovací frekvenci použití za účelem získání výsledků statisticky významná. Informace o tom, jak se změna míry vzorkování v sadě Visual Studio IDE najdete v tématu [jak: Výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md). Další informace o tom, jak změnit vzorkovací frekvenci při použití nástroje pro profilaci příkazového řádku najdete v tématu [časovače](../profiling/timer.md) v [VSPerfCmd](../profiling/vsperfcmd.md) odkaz.