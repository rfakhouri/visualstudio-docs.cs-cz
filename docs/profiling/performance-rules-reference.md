---
title: Referenční dokumentace pravidel výkonu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 59fc9424-76ca-4365-ae47-bb14a736c9c2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 13bcc997f57695c0c8f6e50c755cd485be91c663
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54924201"
---
# <a name="performance-rules-reference"></a>Referenční dokumentace pravidel výkonu
Pravidla výkonu nástrojů pro profilaci poskytují další upozornění a informace o výkonu vaší aplikace. Pravidla výkonu, analýza dat během spuštění profilování, která se shromažďují ze zdrojů, jako jsou Windows a čítače výkonu procesoru. Pravidlo zprávy se zobrazují v okně chybový výstup [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] integrovaného vývojového prostředí. Zprávy jsou uvedeny pomocí jednoho z následujících úrovní pravidlo:  
  
|||  
|-|-|  
|**Chyba**|Několik pravidel generovat chybové zprávy, protože většina problémy s výkonem nejsou chyby rovnou předplatit. Chybová zpráva může znamenat selhání ke shromažďování dat profilace.|  
|**Upozornění**|Upozornění označují oblast vaší aplikace, která může být potenciálně příčiny problémů s výkonem nebo, který může mít užitek z optimalizace.|  
|**Informace o**|Zprávy s informacemi o označuje, že buď analýzy podmínku pravidla, která: nebylo dosaženo této prahové hodnoty generovat chybovou zprávu, nebo že informace ve zprávě je užitečné, ale neodráží problém s výkonem.|  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Pravidla výkonu podle identifikátorů](../profiling/performance-rules-by-id.md)  
  
 Pravidla výkonu nástrojů pro profilaci sady jsou uspořádány do čtyř kategorií:  
  
|||  
|-|-|  
|[Pravidla výkonu použití rozhraní .NET Framework](../profiling/dotnet-framework-usage-performance-rules.md)|Pravidla, která vám pomůže efektivně pomocí rozhraní .NET Framework.|  
|[Pravidla výkonu paměti a stránkování](../profiling/memory-and-paging-performance-rules.md)|Pravidla, která analýza spravované paměti a stránkování vaší aplikace.|  
|[Pravidla používání nástrojů pro profilaci](../profiling/profiling-tools-usage-rules.md)|Pravidla, která vám pomůže efektivně pomocí nástrojů pro profilaci.|  
|[Pravidla výkonu sledování prostředků](../profiling/resource-monitoring-performance-rules.md)|Zprávy s informacemi o využití procesoru a paměti v Profilování spustit.|