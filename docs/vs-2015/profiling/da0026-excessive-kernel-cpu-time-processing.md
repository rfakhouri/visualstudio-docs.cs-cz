---
title: 'DA0026: Čas zpracování procesoru jádra nadměrné | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DA0026
- vs.performance.DA0026
- vs.performance.26
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fef0a3c42be1057bd1217ec676ae43b220d80345
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54768968"
---
# <a name="da0026-excessive-kernel-cpu-time-processing"></a>DA0026: Čas zpracování procesoru jádra nadměrné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id pravidla | TODO |  
| Kategorie | Použití nástroje pro profilaci |  
| Metoda profilace | Vzorkování |  
| Zpráva | Bylo měřeno relativně vysoké množství času procesoru režimu jádra. Zvažte prošetření zdroje s povoleným vzorkováním SysCall. |  
| Typ pravidla | Informace |  
  
 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  
  
## <a name="cause"></a>Příčina  
 Čas procesoru poměr, který se spustil v režimu jádra překročil množství času strávené v uživatelském režimu. Zvažte profilaci znovu a vzorkování počet volání systému (syscalls) a zjistěte příčinu časy spuštění režimu jádra vysoká.  
  
## <a name="rule-description"></a>Popis pravidla  
 Relativně vysoký podíl času stráveného aplikace při spuštění režimu jádra pravděpodobně vyžadovat další šetření. Aplikace v uživatelském režimu přejde do režimu jádra k provádění vstupně-výstupních operací, počkejte podproces nebo proces synchronizace primitiv, nebo proveďte volání systému. Můžete prozkoumat typy systémových volání aplikace provádí a které funkce, které jsou zodpovědné za je, když vyberete možnost shromažďovat zásobníky volání ukázka podle systémových volání.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li prozkoumat typy systémových volání, které vaše aplikace odešle, spusťte profil znovu a vyberte možnost shromažďovat vzorky podle systémových volání. Zobrazit [jak: Výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md) Pokud používáte nástroje pro profilaci zevnitř rozhraní IDE pro další informace. Pokud používáte nástroje pro profilaci z příkazového řádku, najdete v článku **možnosti intervalu vzorkování** část [VSPerfCmd](../profiling/vsperfcmd.md) odkazují nástroje pro téma v příkazovém řádku nástroje pro profilaci.
