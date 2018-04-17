---
title: Zobrazení řádků | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.lines
helpviewer_keywords:
- profiling tools reports, Line view
- profiling tools, Line view
- Lines view
ms.assetid: 71ec0781-6031-4e17-af09-f50226018437
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d7c5565ea8cecb50166536d399fd5a1e7b4f4dd5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="lines-view"></a>Zobrazení řádků
Zobrazení řádků je k dispozici pouze pro profileru data, která nebyla shromážděna pomocí metody vzorkování. Toto zobrazení není k dispozici pro data, která nebyla shromážděna s použitím instrumentace.  
  
 Zobrazení řádků pro vzorkování dat profilu, identifikuje příkaz ve funkci, která byla spuštěna přímo, při ukázku nebyla shromážděna. Zobrazení řádků pro data paměti .NET, identifikuje příkazů, které přidělit paměť.  
  
 Ve zdrojovém souboru příkaz může zahrnovat víc než jeden řádek v souboru zdroje a jeden řádek může obsahovat více než jeden výraz.  
  
 Příkaz je identifikována následující:  
  
-   Zdrojový soubor, který obsahuje příkaz funkce.  
  
-   Funkce, která obsahuje příkaz.  
  
-   Zdrojového řádku, od kterého začne příkaz.  
  
-   Znak v řádku zdroje, od kterého začne příkaz.  
  
-   Řádku zdroje, u které končí příkaz.  
  
-   Znak v řádku zdroje, u které končí příkaz.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení řádků](../profiling/lines-view-sampling-data.md)   
 [Zobrazení řádků – vzorkování](../profiling/lines-view-dotnet-memory-sampling-data.md)   
 [Zobrazení řádků](../profiling/lines-view-contention-data.md)