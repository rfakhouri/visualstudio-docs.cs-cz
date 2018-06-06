---
title: 'DA0029: Nepodporovaná verze CLR | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6ab40efbba692cfa85f14b750d3c853d1112704
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765736"
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
  
## <a name="how-to-fix-violations"></a>Jak opravit porušení  
 Žádné