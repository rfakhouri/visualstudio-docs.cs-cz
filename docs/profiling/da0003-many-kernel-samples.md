---
title: "DA0003: Vysoký počet ukázek jádra | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0003
- vs.performance.DA0003
- vs.performance.3
- vs.performance.rules.DAManyKernelSamples
ms.assetid: c1f46f77-eb95-42e5-b340-d86bc9de41b4
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e7451a5b18b0879a64d92525d5b72a6f4c1ec8cf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0003-many-kernel-samples"></a>DA0003: Vysoký počet ukázek jádra
|||  
|-|-|  
|Id pravidla|DA0003|  
|Kategorie|Použití nástroje pro profilaci|  
|Metod profilace|Vzorkování|  
|Zpráva|Máte vysoký podíl ukázky v režimu jádra. To může znamenat k velkému počtu vstupně-výstupní aktivitu nebo Vysoká rychlost přepínání kontextu. Vezměte v úvahu profilace aplikaci znovu s použitím instrumentace režimu.|  
|Typ pravidla|Informace o|  
  
## <a name="cause"></a>příčina  
 Značná část ukázky zásobníku volání, které byly shromážděny aplikace byly spouštění v režimu jádra. Vezměte v úvahu profilace aplikace pomocí různých metod profilování.  
  
## <a name="rule-description"></a>Popis pravidla  
 V systému Windows mohou být provedeny kódu v režimu jádra nebo v uživatelském režimu. (V režimu jádra zkratka privilegovaném režimu.) Pouze nízké úrovně systému kód, jako jsou ovladače zařízení, se spustí v režimu jádra. Aplikace v uživatelském režimu, můžete přejít do režimu jádra k provedení vstupně-výstupních operací, počkejte vlákna nebo proces synchronizace primitiv, anebo systémová volání.  
  
 Vzorkování je co nejúčinnější, když jsou profilace aplikací, které tráví většinu doba pro jejich pracuje v uživatelském režimu. Počet vzorků, které byly získány při provádění aplikace v režimu jádra, které může naznačovat časté vstupně-výstupních operací nebo může naznačit, že kontext, ve kterém dochází k přepínače. Ani jeden z těchto operací můžete prozkoumat pomocí metody vzorkování. Pokud jsou odebrány příliš mnoho vzorky režimu jádra, nesmí obsahovat data vzorkování dostatek ukázky režimu uživatele je statisticky významný.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vezměte v úvahu profilace aplikace znovu pomocí jedné z následujících možností:  
  
-   Profilu pomocí metody instrumentace.  
  
-   Zvýšit míru vzorkování pokusí shromažďovat další ukázky v uživatelském režimu.