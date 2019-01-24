---
title: 'DA0008: Shromážděno málo vzorků | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 03fd9b6fd794320faf76119616900b79d5bf4333
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54800402"
---
# <a name="da0008-few-samples-collected"></a>DA0008: Shromážděno málo ukázek
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id pravidla | DA0008 |  
| Kategorie | Použití nástroje pro profilaci |  
| Metoda profilace | Vzorkování |  
| Zpráva | Nebyly shromážděny vzorky jenom pár. Zvažte delší spuštění nebo rychlejší vzorkovací frekvenci pro více významné výsledky. |  
| Typ pravidla | Informace |  
  
## <a name="cause"></a>Příčina  
 Při spuštění profilace nebyly shromážděny vzorky jenom pár.  
  
## <a name="rule-description"></a>Popis pravidla  
 Při použití metody vzorkování mají shromažďovat statisticky významná počet vzorků, abyste měli jistotu, že data představují chování skutečný program. Chcete-li minimalizovat chyby vzorkování, doporučujeme shromáždit alespoň 1000 vzorky chování při spuštění programu instrukce. Pokud shromažďujete není dostatek ukázky, které můžete omyl, při analýze dat profilace.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vezměte v úvahu profilování už spuštění aplikace nebo rychlejší vzorkovací frekvenci použití za účelem získání výsledků statisticky významná. Informace o tom, jak se změna míry vzorkování v sadě Visual Studio IDE najdete v tématu [jak: Výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md). Další informace o tom, jak změnit vzorkovací frekvenci při použití nástroje pro profilaci příkazového řádku najdete v tématu [časovače](../profiling/timer.md) v [VSPerfCmd](../profiling/vsperfcmd.md) odkaz.
