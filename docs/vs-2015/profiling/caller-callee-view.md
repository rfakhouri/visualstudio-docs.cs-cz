---
title: Zobrazení volající / volaný | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.callercallee
helpviewer_keywords:
- profiling tools, reports, Caller/Callee view
- profiling tools, Caller/Callee view
- performance reports, Caller/Callee view
- Caller/Callee view
ms.assetid: d3511bcf-cce0-4cbe-aecb-b94c7c80ad1b
caps.latest.revision: 37
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 58aca542571066ecfa9328c9600972665e757150
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176632"
---
# <a name="callercallee-view"></a>Zobrazení olající/volaný
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zobrazení volající/volaný zobrazí profilování informace pro vybrané funkce a jeho funkce pro nadřazené a podřízené. Zobrazení volající/volaný obsahuje tři tabulky:  
  
 **Aktuální funkce** se zobrazí v mřížce střední který ukazuje profilování informace pro vybrané funkce. Hodnoty zahrnují všechna volání funkce, které byly shromážděny během spuštění profilování.  
  
 **Funkce, které volaly aktuální funkcí** se zobrazí v hlavní mřížky, a zobrazuje počet hodnoty vybrané (aktuální) funkce, které byly vytvořeny voláním z funkce volajícího (nadřazené).  
  
 **Funkce, které byly volány aktuální funkcí** se zobrazí v mřížce dolů který ukazuje profilace informace pro volaných (podřízený) funkce vybrané funkce, pokud podřízený funkce byla volána aktuální funkce.  
  
 Sloupce, které jsou k dispozici v zobrazení volající/volaný závisí na metodě profilování (vzorkování nebo instrumentace), která byla použita pro sběr dat a zda shromáždění dat paměti .NET v profilaci spouštět.  
  
 Můžete vybrat jiné funkce jako aktuální funkci ve střední části zobrazení sestav dvojitým kliknutím na některou z funkcí, které jsou uvedeny v ostatních částech dvě zobrazení. Zobrazení sestav se automaticky aktualizuje tak, aby odrážely změny.  
  
 Data lze seřadit klepnutím na názvy sloupců. Zobrazení volající/volaný – lze přidat další sloupce. Další informace najdete v tématu [jak: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md).  
  
## <a name="see-also"></a>Viz také  
 [Volající / volaný zobrazení – vzorkování dat](../profiling/caller-callee-view-sampling-data.md)   
 [Zobrazení volající/volaný – Data instrumentace](../profiling/caller-callee-view-instrumentation-data.md)   
 [Zobrazení volající/volaný – Data instrumentace paměti .NET](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Zobrazení volající/volaný – Data vzorkování paměti .NET](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Volající / volaný zobrazení – Data kolizí](../profiling/caller-callee-view-contention-data.md)
