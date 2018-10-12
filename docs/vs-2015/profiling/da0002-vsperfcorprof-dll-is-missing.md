---
title: 'Da0002: chybí knihovna VSPerfCorProf.dll chybí | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.DA0002
- vs.performance.2
- vs.performance.rules.DAVsPerfCorProfMissing
- vs.performance.rules.DA0002
ms.assetid: 76e614b3-ad7e-4b92-b7be-88dc1329be1d
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86f4738d72cc386e6285dfa96a7f42e906a9a5cd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49242486"
---
# <a name="da0002-vsperfcorprofdll-is-missing"></a>DA0002: Chybí knihovna VSPerfCorProf.dll
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id pravidla | DA0002 KNIHOVNA |  
| Kategorie | Použití nástroje pro profilaci |  
| Metod profilace | Profilace pomocí příkazového řádku nástroje VSPerfCmd a VSPerfASPNETCmd |  
| Zpráva | Zdá se, že soubor byl shromážděn bez správného nastavení proměnných prostředí pomocí VSPerfCLREnv.cmd. Nemůže vyřešit symboly pro spravované binární soubory. |  
| Typ pravidla | Informace |  
  
## <a name="cause"></a>příčina  
 Profileru nelze najít VSPerfCorProf.dll během spuštění profilování. K tomuto upozornění dochází, bez použití nástroje VSPerfCLREnv.cmd inicializovat nezbytné proměnné prostředí se zadáním příkazového řádku nástrojů pro shromažďování dat profileru. Upozornění můžete také provést, pokud jiný profiler je spuštěna při spuštění nástroje pro profilaci.  
  
## <a name="rule-description"></a>Popis pravidla  
 Určité proměnné prostředí musí být nastavena před spuštění profilování profileru, chcete-li vyřešit symboly v rozhraní .NET Framework binární soubory. Toto upozornění naznačuje, že nástroje VSPerfCLREnv.cmd nebyla spuštěna před shromáždění dat profilování. Symboly pro spravované binární soubory nemusí vyřešit. Další informace o používání nástrojů pro profilaci z příkazového řádku najdete v tématu [profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Když provádíte profilaci spravované aplikace pomocí nástroje příkazového řádku v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástroje pro profilaci, spusťte [VSPerfCLREnv](../profiling/vsperfclrenv.md) nástroj pro příkazový řádek před zahájením shromažďování dat.



