---
title: Porozumění hodnotám dat vzorkování | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method
- Profiling Tools, sampling
ms.assetid: fad540a8-24b6-4ff9-91ce-e67e9a58399d
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 91a4a50ecc745c0b56167d6a5dbb1932af7ed2bf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68145427"
---
# <a name="understanding-sampling-data-values"></a>Porozumění hodnotám dat vzorkování
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

*Vzorkování* metodu profilace [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů pro profilaci sady přerušuje procesor počítače v nastavených intervalech a shromažďuje zásobník volání funkce. A *zásobníku volání* je dynamické strukturu, která uchovává informace o funkcích, které jsou spuštěny na procesor.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
  Profiler analýza určí, zda procesor spouští kód v cílovém procesu. Pokud procesor není spouštění kódu v cílovém procesu, se zahodí vzorku.  
  
  Pokud procesor spouští cílový kód, profiler zvýší čítače vzorků pro každou funkci v zásobníku volání. V době, která je vzorek odebírán jenom jednu funkci v zásobníku volání je právě spouští kód. Další funkce v zásobníku jsou nadřazené položky v hierarchii volání funkce, která čekají na své děti se vraťte.  
  
  Pro událost vzorku, profiler přírůstky *exkluzivní* počet funkce, která se právě probíhá jeho pokynů vzorků. Protože exkluzivní ukázky je také součástí celkové (*včetně*) ukázky funkce, včetně ukázkové počet aktuálně aktivních funkce se také zvýší.  
  
  Profiler zvýší počet vzorků včetně všech funkcí v zásobníku volání.  
  
## <a name="inclusive-samples"></a>Celkových vzorků  
 Celkový počet vzorků, které byly shromážděny během spuštění funkce cíl.  
  
 To zahrnuje ukázky, které byly shromážděny během přímé provádění kódu funkce a ukázky, které byly shromážděny během spuštění funkce podřízený, které jsou volány cílová funkce.  
  
## <a name="exclusive-samples"></a>Výhradní vzorky  
 Počet vzorků, které byly shromážděny během spouštění s přímým přístupem pokyny cílová funkce.  
  
 Výhradní vzorky nezahrnují ukázky, které byly shromážděny během spuštění funkce, které jsou volány cílová funkce.  
  
## <a name="inclusive-percent"></a>Celkové procento  
 Procento celkový počet celkových vzorků při spuštění profilace, které jsou celkových vzorků rozsah funkce nebo data.  
  
## <a name="exclusive-percent"></a>Výhradní procent  
 Procento z celkového počtu výhradních vzorků při spuštění profilace, které jsou exkluzivní vzorky rozsah funkce nebo data.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)   
 [Analýza dat nástrojů pro měření výkonu](../profiling/analyzing-performance-tools-data.md)
