---
title: "Značky rozpětí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.markers.span
ms.assetid: 736b7765-9c71-44d7-85e5-79787d13d91c
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fff5fdc6b523038945d94d61e27c083278d6fb25
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="span-markers"></a>Značky rozpětí
Značku span představuje smysluplný fázi aplikace. Například můžete rozpětí představují interval čas, během kterého probíhá zpracování konkrétní pracovní položky. Jeho délka představuje dobu trvání odpovídající fázi aplikace. Tento obrázek ukazuje rozpětí v Concurrency Visualizer:  
  
 ![Značku span v Concurrency Visualizer](../profiling/media/cvmarkerspan.png "CVMarkerSpan")  
Značku span v vizualizér souběžnosti  
  
## <a name="span-category"></a>Kategorie rozpětí  
 Značku span se zobrazí v jedné z pěti různých barev, v závislosti na jeho kategorii. Barvy se opakuje, pokud existuje více než pět kategorií. Kategorie může být jakékoli celé číslo. Tento obrázek ukazuje pět možných barev:  
  
 ![Pět rozpětí v různých kategorií](../profiling/media/cvmarkerspancategory.png "CVMarkerSpanCategory")  
Barvy nejprve pěti kategorií rozpětí  
  
## <a name="span-aggregation-markers"></a>Agregace značky rozpětí  
 Někdy rozpětí značek tak dojít blízko sebe navzájem v Concurrency Visualizer, že se nemůže být vykreslován jednotlivě. Pokud k tomu dojde, šedá *značky span agregace* , se zobrazí představuje základní rozpětí. Pokud se ukazatel myši na jednu z těchto ikon, zobrazí popisek počet základní rozsahy, které představuje. Pokud chcete zobrazit rozsahy, přiblížení. Pokud přiblížit úplně a stále získat značku span agregace, můžete zobrazit základní značky span v [sestava značek](../profiling/markers-report.md). Na tomto obrázku značky span agregace:  
  
 ![Agregace span značky v Concurrency Visualizer](../profiling/media/cvmarkerspanaggregate.png "CVMarkerSpanAggregate")  
Značka span agregace  
  
## <a name="see-also"></a>Viz také  
 [Značky Vizualizéru souběžnosti](../profiling/concurrency-visualizer-markers.md)   
 [SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md)