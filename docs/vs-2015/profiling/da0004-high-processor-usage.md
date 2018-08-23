---
title: 'DA0004: Vysoké využití procesoru | Dokumentace Microsoftu'
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
- vs.performance.rules.DAHighProcessorUsage
- vs.performance.rules.DA0004
- vs.performance.DA0004
- vs.performance.4
ms.assetid: 2c4fb569-929e-4f1d-8c50-b590ee371351
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 759ba305335c75591bf975e40f011f31edd1bdb5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674685"
---
# <a name="da0004-high-processor-usage"></a>DA0004: Vysoké využití procesoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [DA0004: vysoké využití procesoru](https://docs.microsoft.com/visualstudio/profiling/da0004-high-processor-usage).  
  
Id pravidla | DA0004 |  
| Kategorie | Použití nástroje pro profilaci |  
| Metod profilace | Instrumentace vzorkování |  
| Zpráva | Využití procesoru je trvale vyšší než 75 %. Zvažte použití režimu vzorkování pro aplikace vázané na procesor. |  
| Typ pravidla | Informace |  
  
 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Využití procesoru (CPU) bylo velmi vysokou v profilaci dat, která byla shromážděna pomocí metody instrumentace. Zvažte použití při profilování Procesorem vázán aplikace metoda profilování vzorkování.  
  
## <a name="rule-description"></a>Popis pravidla  
 Během tohoto spuštění profilování byly konzistentní velmi vytížený procesoru (nebo procesory). Vysoké využití procesoru můžete určit aplikace vázané na procesor. Instrumentovaná profily nejsou obvykle nejúčinnější způsob pro scénáře využití procesoru. Vzorkování je obvykle efektivnější, pokud provádíte profilaci aplikace, které tráví většinu svého času provádění instrukcí na procesor.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zvažte profilaci vaší aplikace znovu pomocí metody odběru vzorků namísto metody instrumentace, pokud vyžadujete funkce časování nebo více zájem o porozumění vstupu a výstupu než problémových míst procesoru.




