---
title: "DA0002: Chybí VSPerfCorProf.dll | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0002
- vs.performance.2
- vs.performance.rules.DAVsPerfCorProfMissing
- vs.performance.rules.DA0002
ms.assetid: 76e614b3-ad7e-4b92-b7be-88dc1329be1d
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 348fe328caed15da059ae5d3e9dec3b9b334e4dd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0002-vsperfcorprofdll-is-missing"></a>DA0002: Chybí knihovna VSPerfCorProf.dll
|||  
|-|-|  
|Id pravidla|DA0002|  
|Kategorie|Použití nástroje pro profilaci|  
|Metod profilace|Profilace pomocí nástroje příkazového řádku VSPerfCmd a VSPerfASPNETCmd|  
|Zpráva|Zdá se, že soubor byl shromážděn bez správně nastavení proměnných prostředí pomocí VSPerfCLREnv.cmd. Symboly pro spravované binární soubory nemusí vyřešit.|  
|Typ pravidla|Informace o|  
  
## <a name="cause"></a>příčina  
 Během spuštění profilování nebyla nalezena VSPerfCorProf.dll profileru. Toto upozornění se zobrazí v případě nástroje příkazového řádku pro shromažďování dat profileru používají bez použití nástroje VSPerfCLREnv.cmd k chybě při inicializaci nezbytné proměnné prostředí. Toto upozornění můžete také provést, pokud jiné profileru běží při spuštění nástroje pro profilaci.  
  
## <a name="rule-description"></a>Popis pravidla  
 Určité proměnné prostředí musí být nastavená před spuštění profilace pro profileru přeložit symboly v binárních souborech rozhraní .NET Framework. Toto upozornění naznačuje, že nástroj VSPerfCLREnv.cmd nebyl spuštěn před profilování data nebyla shromážděna. Symboly pro spravované binární soubory nemusí vyřešit. Další informace o použití nástrojů pro profilaci z příkazového řádku najdete v tématu [profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Když jsou profilace spravovaných aplikací pomocí nástroje příkazového řádku v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci, spusťte [vsperfclrenv –](../profiling/vsperfclrenv.md) nástroj pro příkazový řádek před zahájením shromažďování dat.