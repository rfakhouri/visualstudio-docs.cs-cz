---
title: 'DA0026: Nadměrný zpracování procesoru jádra čas | Dokumentace Microsoftu'
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
- vs.performance.rules.DA0026
- vs.performance.DA0026
- vs.performance.26
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29eda10403e2d09f5a1bdf67911e1f2ae58bd9f0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666749"
---
# <a name="da0026-excessive-kernel-cpu-time-processing"></a>DA0026: Nadměrný čas zpracování procesoru jádra
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [DA0026: nadměrný zpracování procesoru jádra čas](https://docs.microsoft.com/visualstudio/profiling/da0026-excessive-kernel-cpu-time-processing).  
  
Id pravidla | TODO |  
| Kategorie | Použití nástroje pro profilaci |  
| Metoda profilace | Vzorkování |  
| Zpráva | Bylo měřeno relativně vysoké množství času procesoru režimu jádra. Zvažte prošetření zdroje s povoleným vzorkováním SysCall. |  
| Typ pravidla | Informace |  
  
 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Čas procesoru poměr, který se spustil v režimu jádra překročil množství času strávené v uživatelském režimu. Zvažte profilaci znovu a vzorkování počet volání systému (syscalls) a zjistěte příčinu časy spuštění režimu jádra vysoká.  
  
## <a name="rule-description"></a>Popis pravidla  
 Relativně vysoký podíl času stráveného aplikace při spuštění režimu jádra pravděpodobně vyžadovat další šetření. Aplikace v uživatelském režimu přejde do režimu jádra k provádění vstupně-výstupních operací, počkejte podproces nebo proces synchronizace primitiv, nebo proveďte volání systému. Můžete prozkoumat typy systémových volání aplikace provádí a které funkce, které jsou zodpovědné za je, když vyberete možnost shromažďovat zásobníky volání ukázka podle systémových volání.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li prozkoumat typy systémových volání, které vaše aplikace odešle, spusťte profil znovu a vyberte možnost shromažďovat vzorky podle systémových volání. V tématu [jak: Zvolte událostí vzorkování](../profiling/how-to-choose-sampling-events.md) Pokud používáte nástroje pro profilaci zevnitř rozhraní IDE pro další informace. Pokud používáte nástroje pro profilaci z příkazového řádku, najdete v článku **možnosti intervalu vzorkování** část [VSPerfCmd](../profiling/vsperfcmd.md) odkazují nástroje pro téma v příkazovém řádku nástroje pro profilaci.



