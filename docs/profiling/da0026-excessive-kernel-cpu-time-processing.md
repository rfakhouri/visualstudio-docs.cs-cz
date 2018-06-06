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
ms.openlocfilehash: 4a571b0eee0a0cdd4b6e232dc13bd8e8923da805
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750178"
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
  
## <a name="how-to-fix-violations"></a>Jak opravit porušení  
 K prozkoumání druhy systémová volání, které vaše aplikace umožňuje spustit profil znovu a vyberte možnost ke shromáždění ukázky podle systémová volání. V tématu [postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md) Pokud používáte nástrojů pro profilaci uvnitř IDE pro další informace. Pokud používáte nástrojů pro profilaci z příkazového řádku, přečtěte si téma **ukázkové interval možnosti** části [VSPerfCmd](../profiling/vsperfcmd.md) článek v nástrojích pro profilaci odkaz nástroje příkazového řádku.