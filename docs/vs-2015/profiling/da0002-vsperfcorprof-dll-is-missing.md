---
title: 'DA0002: VSPerfCorProf.dll chybí | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.DA0002
- vs.performance.2
- vs.performance.rules.DAVsPerfCorProfMissing
- vs.performance.rules.DA0002
ms.assetid: 76e614b3-ad7e-4b92-b7be-88dc1329be1d
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5723506415a0ddbf816b896e23e93eaa706bf7e7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54792920"
---
# <a name="da0002-vsperfcorprofdll-is-missing"></a>DA0002: VSPerfCorProf.dll is missing
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id pravidla | DA0002 KNIHOVNA |  
| Kategorie | Použití nástroje pro profilaci |  
| Metod profilace | Profilace pomocí příkazového řádku nástroje VSPerfCmd a VSPerfASPNETCmd |  
| Zpráva | Zdá se, že soubor byl shromážděn bez správného nastavení proměnných prostředí pomocí VSPerfCLREnv.cmd. Nemůže vyřešit symboly pro spravované binární soubory. |  
| Typ pravidla | Informace |  
  
## <a name="cause"></a>Příčina  
 Profileru nelze najít VSPerfCorProf.dll během spuštění profilování. K tomuto upozornění dochází, bez použití nástroje VSPerfCLREnv.cmd inicializovat nezbytné proměnné prostředí se zadáním příkazového řádku nástrojů pro shromažďování dat profileru. Upozornění můžete také provést, pokud jiný profiler je spuštěna při spuštění nástroje pro profilaci.  
  
## <a name="rule-description"></a>Popis pravidla  
 Určité proměnné prostředí musí být nastavena před spuštění profilování profileru, chcete-li vyřešit symboly v rozhraní .NET Framework binární soubory. Toto upozornění naznačuje, že nástroje VSPerfCLREnv.cmd nebyla spuštěna před shromáždění dat profilování. Symboly pro spravované binární soubory nemusí vyřešit. Další informace o používání nástrojů pro profilaci z příkazového řádku najdete v tématu [profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Když provádíte profilaci spravované aplikace pomocí nástroje příkazového řádku v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástroje pro profilaci, spusťte [VSPerfCLREnv](../profiling/vsperfclrenv.md) nástroj pro příkazový řádek před zahájením shromažďování dat.
