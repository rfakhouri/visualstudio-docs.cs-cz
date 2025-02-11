---
title: 'DA0002: VSPerfCorProf.dll chybí | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0002
- vs.performance.2
- vs.performance.rules.DAVsPerfCorProfMissing
- vs.performance.rules.DA0002
ms.assetid: 76e614b3-ad7e-4b92-b7be-88dc1329be1d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: aa263f6ceab515627fd33070517e3393aeec419d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62936726"
---
# <a name="da0002-vsperfcorprofdll-is-missing"></a>DA0002: Chybí knihovna VSPerfCorProf.dll

|||
|-|-|
|Id pravidla|DA0002|
|Kategorie|Použití nástroje pro profilaci|
|Metod profilace|Použití nástroje VSPerfCmd a VSPerfASPNETCmd příkazového řádku pro profilaci|
|Zpráva|Zdá se, že soubor byl shromážděn bez správného nastavení proměnných prostředí pomocí *VSPerfCLREnv.cmd*. Nemůže vyřešit symboly pro spravované binární soubory.|
|Typ pravidla|Informace o|

## <a name="cause"></a>Příčina
 Nelze najít profiler *VSPerfCorProf.dll* během spuštění profilování. K tomuto upozornění dochází v případě nástroje příkazového řádku pro shromažďování dat profileru používají bez použití *VSPerfCLREnv.cmd* nástroj k inicializaci nezbytné proměnné prostředí. Upozornění můžete také provést, pokud jiný profiler je spuštěna při spuštění nástroje pro profilaci.

## <a name="rule-description"></a>Popis pravidla
 Určité proměnné prostředí musí být nastavena před spuštění profilování profileru, chcete-li vyřešit symboly v rozhraní .NET Framework binární soubory. Toto upozornění naznačuje, že *VSPerfCLREnv.cmd* nástroj nebyla spuštěna před shromáždění dat profilování. Symboly pro spravované binární soubory nemusí vyřešit. Další informace o používání nástrojů pro profilaci z příkazového řádku najdete v tématu [profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Když provádíte profilaci spravované aplikace pomocí nástroje příkazového řádku v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje pro profilaci, spusťte [VSPerfCLREnv](../profiling/vsperfclrenv.md) nástroj pro příkazový řádek před zahájením shromažďování dat.