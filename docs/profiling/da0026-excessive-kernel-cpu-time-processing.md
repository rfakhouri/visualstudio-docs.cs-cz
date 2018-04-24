---
title: 'DA0026: Nadměrný jádra procesoru čas zpracování | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0026
- vs.performance.DA0026
- vs.performance.26
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 10f7f38bbf0655099e3c90f3893c34be39ef4b28
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="da0026-excessive-kernel-cpu-time-processing"></a>DA0026: Nadměrný čas zpracování procesoru jádra
|||  
|-|-|  
|Id pravidla|TODO|  
|Kategorie|Použití nástroje pro profilaci|  
|Metoda profilace|Vzorkování|  
|Zpráva|Měří se poměrně vysoké množství času procesoru režimu jádra. Měli byste prověřit zdroji s SysCall vzorkování povolena.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Čas procesoru poměru, který byl spuštěn v režimu jádra překročena množství času strávené v uživatelském režimu. Zvažte profilace znovu a vzorkování počet systémová volání (syscalls) a zjistěte příčinu časy spuštění režimu vysoké jádra.  
  
## <a name="rule-description"></a>Popis pravidla  
 Relativně vysoký podíl času stráveného aplikace při provádění režimu jádra je důvod k další šetření. Aplikace v uživatelském režimu přejde do režimu jádra k provedení vstupně-výstupních operací, počkejte vlákna nebo proces synchronizace primitiv, anebo systémová volání. Můžete prozkoumat druhy systémová volání umožňuje aplikace a funkce, které jsou zodpovědní za je, když vyberete možnost získat zásobníky volání ukázka podle systémová volání.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 K prozkoumání druhy systémová volání, které vaše aplikace umožňuje spustit profil znovu a vyberte možnost ke shromáždění ukázky podle systémová volání. V tématu [postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md) Pokud používáte nástrojů pro profilaci uvnitř IDE pro další informace. Pokud používáte nástrojů pro profilaci z příkazového řádku, najdete v článku **možnosti intervalu vzorkování** části [VSPerfCmd](../profiling/vsperfcmd.md) téma v nástrojích pro profilaci příkazového řádku nástroje odkaz.