---
title: Porozumění hodnotám dat vzorkování | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- sampling profiling method
- Profiling Tools, sampling
ms.assetid: fad540a8-24b6-4ff9-91ce-e67e9a58399d
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86458fcc630b023cd1495b91a388fe245b71d772
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49877631"
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
 [Postupy: výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)   
 [Analýza dat nástrojů pro měření výkonu](../profiling/analyzing-performance-tools-data.md)



