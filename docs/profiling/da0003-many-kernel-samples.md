---
title: 'DA0003: Počet ukázek jádra | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0003
- vs.performance.DA0003
- vs.performance.3
- vs.performance.rules.DAManyKernelSamples
ms.assetid: c1f46f77-eb95-42e5-b340-d86bc9de41b4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 895fd206a6ca816726606ebc57e2fc0a865ee2f8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923078"
---
# <a name="da0003-many-kernel-samples"></a>DA0003: Počet ukázek jádra

|||  
|-|-|  
|Id pravidla|DA0003|  
|Kategorie|Použití nástroje pro profilaci|  
|Metod profilace|Vzorkování|  
|Zpráva|Máte vysoký podíl vzorků v režimu jádra. To může znamenat velký objem vstupně-výstupních operací aktivity nebo vysokou míru přepínání kontextu. Zvažte profilaci vaší aplikace znovu pomocí režimu instrumentace.|  
|Typ pravidla|Informace o|  

## <a name="cause"></a>Příčina  
 Podstatnou část ukázky zásobníku volání, které byly shromážděny pro aplikaci se spouští v režimu jádra. Zvažte profilaci vaší aplikace pomocí různých metod profilace.  

## <a name="rule-description"></a>Popis pravidla  
 Ve Windows lze kód spustit v režimu jádra nebo v uživatelském režimu. (V režimu jádra zkratka privilegovaném režimu.) Pouze nižší úrovně systému kódu, jako jsou ovladače zařízení, se spustí v režimu jádra. Aplikace v uživatelském režimu, můžete přejít do režimu jádra k provádění vstupně-výstupních operací, počkejte podproces nebo proces synchronizace primitiv, nebo proveďte volání systému.  

 Vzorkování je nejúčinnější, když se profilování aplikací, které tráví většinu svého času věnovat práci v uživatelském režimu. Počet vzorků, které byly získány při spouštění aplikace v režimu jádra, které můžete určit časté vstupně-výstupních operací nebo mohou signalizovat tohoto kontextu, ve kterém dochází k přepínači. Ani jeden z těchto operací můžete prozkoumat pomocí metody vzorkování. Pokud příliš mnoho vzorky režimu jádra jsou odebrány, vzorkování dat nemusí obsahovat dostatek uživatelského režimu vzorků statisticky významná.  

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zvažte profilaci vaší aplikace znovu pomocí jedné z následujících možností:  

-   Profilu pomocí metody instrumentace.  

-   Zvyšte vzorkovací frekvenci se pokouší shromažďovat další ukázky v uživatelském režimu.