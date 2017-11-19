---
title: "Volající volaný – zobrazení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.callercallee
helpviewer_keywords:
- profiling tools, reports, Caller/Callee view
- profiling tools, Caller/Callee view
- performance reports, Caller/Callee view
- Caller/Callee view
ms.assetid: d3511bcf-cce0-4cbe-aecb-b94c7c80ad1b
caps.latest.revision: "32"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0792f59f02c5b75247d5066b132cf1072d37c76a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="callercallee-view"></a>Volající/volaný – zobrazení
Zobrazení volající/volaný zobrazí profilování informace o vybrané funkce a její nadřazené a podřízené funkce. Zobrazení volající/volaný obsahuje tři mřížky:  
  
 **Funkci Current** se zobrazí v prostředním mřížky a ukazuje profilace informace o vybrané funkce. Hodnoty zahrnují všechna volání funkce, které byly shromážděny v profilaci spustit.  
  
 **Funkce, které volá funkci current** se zobrazí v horní mřížky, a zobrazuje počet hodnot vybrané (aktuální) funkce, které byly vygenerovány volání z funkce volající (nadřazené).  
  
 **Funkce, které byly volá funkci current** se zobrazí v mřížce dole ale zobrazí při volání funkce podřízené aktuální funkcí profilace informace pro funkce volaný (podřízená) vybrané funkce.  
  
 Sloupce, které jsou k dispozici v zobrazení volající/volaný závisí na profilování metody (vzorkování nebo instrumentace), která se používá ke shromažďování dat a jestli dat paměti .NET nebyla shromážděna v profilaci spustit.  
  
 Můžete vybrat jiné funkce na funkci aktuální v střední část zobrazení sestavy, a dvakrát klikněte na některou z funkcí, které jsou uvedeny v další dvě části tohoto zobrazení. Zobrazení sestavy se automaticky aktualizuje, aby se projevily změny.  
  
 Data můžete seřadit kliknutím na názvy sloupců. Zobrazení volající/volaný lze přidat další sloupce. Další informace najdete v tématu [postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md).  
  
## <a name="see-also"></a>Viz také  
 [Volající / volaný – zobrazení – Data vzorkování](../profiling/caller-callee-view-sampling-data.md)   
 [Zobrazení volající/volaný – Data instrumentace](../profiling/caller-callee-view-instrumentation-data.md)   
 [Zobrazení volající/volaný – Data instrumentace paměti NET](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Zobrazení volající/volaný – Data vzorkování paměti .NET](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Volající / volaný – zobrazení – Data kolizí](../profiling/caller-callee-view-contention-data.md)