---
title: "DA0026: Nadměrný jádra procesoru čas zpracování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0026
- vs.performance.DA0026
- vs.performance.26
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bf419874b0758f56927b570e292b42f35137d53a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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