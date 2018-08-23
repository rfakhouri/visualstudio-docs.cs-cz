---
title: 'Da0003: vysoký počet Ukázek jádra | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0003
- vs.performance.DA0003
- vs.performance.3
- vs.performance.rules.DAManyKernelSamples
ms.assetid: c1f46f77-eb95-42e5-b340-d86bc9de41b4
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd4412fc120eb0a0fa039ac91bec4da4ba4a6f44
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672972"
---
# <a name="da0003-many-kernel-samples"></a>DA0003: Vysoký počet ukázek jádra
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [da0003 vysoký počet: počet ukázek jádra](https://docs.microsoft.com/visualstudio/profiling/da0003-many-kernel-samples).  
  
Id pravidla | DA0003 VYSOKÝ POČET |  
| Kategorie | Použití nástroje pro profilaci |  
| Metod profilace | Vzorkování |  
| Zpráva | Máte vysoký podíl vzorků v režimu jádra. To může znamenat velký objem vstupně-výstupních operací aktivity nebo vysokou míru přepínání kontextu. Zvažte profilaci vaší aplikace znovu pomocí režimu instrumentace. |  
| Typ pravidla | Informace |  
  
## <a name="cause"></a>příčina  
 Podstatnou část ukázky zásobníku volání, které byly shromážděny pro aplikaci se spouští v režimu jádra. Zvažte profilaci vaší aplikace pomocí různých metod profilace.  
  
## <a name="rule-description"></a>Popis pravidla  
 Ve Windows lze kód spustit v režimu jádra nebo v uživatelském režimu. (V režimu jádra zkratka privilegovaném režimu.) Pouze nižší úrovně systému kódu, jako jsou ovladače zařízení, se spustí v režimu jádra. Aplikace v uživatelském režimu, můžete přejít do režimu jádra k provádění vstupně-výstupních operací, počkejte podproces nebo proces synchronizace primitiv, nebo proveďte volání systému.  
  
 Vzorkování je nejúčinnější, když se profilování aplikací, které tráví většinu svého času věnovat práci v uživatelském režimu. Počet vzorků, které byly získány při spouštění aplikace v režimu jádra, které můžete určit časté vstupně-výstupních operací nebo mohou signalizovat tohoto kontextu, ve kterém dochází k přepínači. Ani jeden z těchto operací můžete prozkoumat pomocí metody vzorkování. Pokud příliš mnoho vzorky režimu jádra jsou odebrány, vzorkování dat nemusí obsahovat dostatek uživatelského režimu vzorků statisticky významná.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zvažte profilaci vaší aplikace znovu pomocí jedné z následujících možností:  
  
-   Profilu pomocí metody instrumentace.  
  
-   Zvyšte vzorkovací frekvenci se pokouší shromažďovat další ukázky v uživatelském režimu.



