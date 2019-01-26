---
title: 'DA0026: Čas zpracování procesoru jádra nadměrné | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0026
- vs.performance.DA0026
- vs.performance.26
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a22f797f8099da7b33afb0e0b6f05bd932f67c1c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971961"
---
# <a name="da0026-excessive-kernel-cpu-time-processing"></a>DA0026: Čas zpracování procesoru jádra nadměrné

|||  
|-|-|  
|Id pravidla|TODO|  
|Kategorie|Použití nástroje pro profilaci|  
|Metoda profilace|Vzorkování|  
|Zpráva|Bylo měřeno relativně vysoké množství času procesoru režimu jádra. Zvažte prošetření zdroje s povoleným vzorkováním SysCall.|  
|Typ pravidla|Informace o|  

 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  

## <a name="cause"></a>Příčina  
 Čas procesoru poměr, který se spustil v režimu jádra překročil množství času strávené v uživatelském režimu. Zvažte profilaci znovu a vzorkování počet volání systému (syscalls) a zjistěte příčinu časy spuštění režimu jádra vysoká.  

## <a name="rule-description"></a>Popis pravidla  
 Relativně vysoký podíl času stráveného aplikace při spuštění režimu jádra pravděpodobně vyžadovat další šetření. Aplikace v uživatelském režimu přejde do režimu jádra k provádění vstupně-výstupních operací, počkejte podproces nebo proces synchronizace primitiv, nebo proveďte volání systému. Můžete prozkoumat typy systémových volání aplikace provádí a které funkce, které jsou zodpovědné za je, když vyberete možnost shromažďovat zásobníky volání ukázka podle systémových volání.  

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li prozkoumat typy systémových volání, které vaše aplikace odešle, spusťte profil znovu a vyberte možnost shromažďovat vzorky podle systémových volání. Zobrazit [jak: Výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md) Pokud používáte nástroje pro profilaci zevnitř rozhraní IDE pro další informace. Pokud používáte nástroje pro profilaci z příkazového řádku, najdete v článku **ukázkový možnosti intervalu** část [VSPerfCmd](../profiling/vsperfcmd.md) článek v referenční dokumentace nástrojů příkazového řádku nástrojů pro profilaci sady.