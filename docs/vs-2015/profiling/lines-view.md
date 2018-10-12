---
title: Zobrazení řádků | Dokumentace Microsoftu
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
- vs.performance.view.lines
helpviewer_keywords:
- profiling tools reports, Line view
- profiling tools, Line view
- Lines view
ms.assetid: 71ec0781-6031-4e17-af09-f50226018437
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fdf3249974f2e04cc3794c3437b0d31cef7b9ef9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205130"
---
# <a name="lines-view"></a>Zobrazení řádků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zobrazení řádků je k dispozici pouze pro data profileru, která byla shromážděna pomocí metody vzorkování. Zobrazení není k dispozici pro data, která byla shromážděna pomocí instrumentace.  
  
 Zobrazení řádků pro vzorkování dat profilu, identifikuje příkaz ve funkci, která byla spuštěna přímo po shromáždění vzorku. Zobrazení řádků pro data paměti .NET, identifikuje příkazy, které přidělují paměť.  
  
 Ve zdrojovém souboru příkaz se týkají více než jeden řádek ve zdrojovém souboru a jeden řádek může obsahovat více než jeden výraz.  
  
 Příkaz je identifikován následující:  
  
-   Zdrojový soubor, který obsahuje Function – příkaz  
  
-   Funkce, která obsahuje příkaz.  
  
-   Zdrojový řádek, ve kterém se spustí příkaz.  
  
-   Znak ve zdrojovém řádku, ve kterém se spustí příkaz.  
  
-   Řádku zdroje, u které končí příkaz.  
  
-   Znak ve zdrojovém řádku, kdy příkaz skončí.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení řádků](../profiling/lines-view-sampling-data.md)   
 [Zobrazení řádků – vzorkování](../profiling/lines-view-dotnet-memory-sampling-data.md)   
 [Zobrazení řádků](../profiling/lines-view-contention-data.md)



