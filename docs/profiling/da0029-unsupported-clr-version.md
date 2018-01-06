---
title: "DA0029: Nepodporovaná verze CLR | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e11b053b867679f65052af5dea93799e4b356892
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: Nepodporovaná verze CLR
|||  
|-|-|  
|Id pravidla|DA0029|  
|Kategorie|Použití nástroje pro profilaci|  
|Metoda profilace|Profilace z příkazového řádku|  
|Zpráva|Během kolekce byla zjištěna nepodporovaná verze CLR. Spravované symboly nemusí správně vyřešit.|  
|Typ pravidla|Informace.|  
  
## <a name="cause"></a>příčina  
 Pokoušíte se profil aplikace, která používá [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)] není podporována nástrojích pro profilaci.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto upozornění se zobrazí, protože nástrojů pro profilaci nelze vyřešit symboly pro spravovaný kód spuštěný v aplikaci. Nástroje pro profilaci nelze vyřešit symboly spravovaného kódu pro aplikace, které jsou spuštěny [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)].  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Žádné