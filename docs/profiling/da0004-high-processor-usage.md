---
title: 'DA0004: Vysoké využití procesoru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAHighProcessorUsage
- vs.performance.rules.DA0004
- vs.performance.DA0004
- vs.performance.4
ms.assetid: 2c4fb569-929e-4f1d-8c50-b590ee371351
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5800acfded9d500c68a0e071ffa6501d6b3c77e
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749607"
---
# <a name="da0004-high-processor-usage"></a>DA0004: Vysoké využití procesoru
|||  
|-|-|  
|Id pravidla|DA0004|  
|Kategorie|Použití nástroje pro profilaci|  
|Metod profilace|Instrumentace<br /><br /> Vzorkování|  
|Zpráva|Vaše využití procesoru je větší než 75 % konzistentně. Zvažte použití režimu vzorkování pro aplikace vázané na procesor.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Využití procesoru (CPU) byla v profilaci data, která nebyla shromážděna pomocí metody instrumentace vysoká. Zvažte použití vzorkování metoda profilace při profilace procesor vázaný aplikace.  
  
## <a name="rule-description"></a>Popis pravidla  
 V průběhu této spuštění profilování byl konzistentně zaneprázdněn procesoru (nebo procesory). Vysoké využití procesoru může znamenat aplikace vázané na procesor. Instrumentované profily nejsou co nejúčinnější způsob, jak prozkoumat scénáře využití procesoru. Vzorkování je účinnější, pokud jsou profilace aplikací, které stráví velkou část doba pro jejich provádění pokyny na procesor.  
  
## <a name="how-to-fix-violations"></a>Jak opravit porušení  
 Vezměte v úvahu profilace aplikace znovu pomocí metody vzorkování místo metody instrumentace, pokud požadujete časování funkce, nebo vás zajímá více Principy vstupu a výstupu než kritické body procesoru.