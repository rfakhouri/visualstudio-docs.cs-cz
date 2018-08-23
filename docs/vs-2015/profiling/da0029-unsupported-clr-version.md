---
title: 'DA0029: Nepodporovaná verze CLR | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df5deda533c21033d26af4b8dc08d98a5dafc583
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628201"
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: Nepodporovaná verze CLR
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [DA0029: Nepodporovaná verze CLR](https://docs.microsoft.com/visualstudio/profiling/da0029-unsupported-clr-version).  
  
Id pravidla | DA0029 |  
| Kategorie | Použití nástroje pro profilaci |  
| Metoda profilace | Profilace z příkazového řádku |  
| Zpráva | Během shromažďování byla zjištěna nepodporovaná verze CLR. Spravované symboly nemůže vyřešit správně. |  
| Typ pravidla | Informace o. |  
  
## <a name="cause"></a>příčina  
 Pokoušíte se profil aplikace, která se používá [!INCLUDE[net_v11_long](../includes/net-v11-long-md.md)] , která není podporována nástrojů pro profilaci.  
  
## <a name="rule-description"></a>Popis pravidla  
 K tomuto upozornění dochází, protože nástrojů pro profilaci, nebude možné vyřešit symboly pro spravovaný kód spuštěný v aplikaci. Nástroje pro profilaci nemůže vyřešit symboly spravovaného kódu pro aplikace, které jsou spuštěny [!INCLUDE[net_v11_long](../includes/net-v11-long-md.md)].  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Žádné



