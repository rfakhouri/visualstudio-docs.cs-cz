---
title: 'DA0008: Shromážděné málo ukázek | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb8471728adda5bb141422833c96e0278fed8e5f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="da0008-few-samples-collected"></a>DA0008: Shromážděno málo ukázek
|||  
|-|-|  
|Id pravidla|DA0008|  
|Kategorie|Použití nástroje pro profilaci|  
|Metoda profilace|Vzorkování|  
|Zpráva|Bylo shromážděno pouze jenom počtu vzorků. Vezměte v úvahu delší spustit nebo rychlejší vzorkovací frekvenci větších výsledků.|  
|Typ pravidla|Informace o|  
  
## <a name="cause"></a>příčina  
 Několika ukázky byly shromážděny v profilaci spustit.  
  
## <a name="rule-description"></a>Popis pravidla  
 Při použití metody vzorkování, mají shromažďovat statisticky velký počet vzorků, abyste měli jistotu, že data představují skutečné program chování. Chcete-li minimalizovat chyby vzorkování, se pokuste shromažďovat alespoň 1 000 ukázky chování při spuštění programu instrukcí. Pokud jste neshromažďují dostatek ukázky, vám může omyl, při analýze dat profilování.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zvažte profilace již spuštění aplikace nebo pomocí rychlejší vzorkovací frekvenci pro získání statisticky významný výsledků. Informace o tom, jak změnit vzorkovací frekvenci v integrovaném vývojovém prostředí sady Visual Studio najdete v tématu [postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md). Další informace o tom, jak změnit vzorkovací frekvenci při použití nástroje pro profilaci příkazového řádku najdete v tématu [časovače](../profiling/timer.md) v [VSPerfCmd](../profiling/vsperfcmd.md) odkaz.