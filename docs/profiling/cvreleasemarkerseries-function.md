---
title: "Cvreleasemarkerseries – funkce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords: CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d295d73560a560caa7f374965a280cf48ad66c2d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="cvreleasemarkerseries-function"></a>CvReleaseMarkerSeries – funkce
Uvolní řady značky. Nepoužívejte značky řady objektu po vydání aplikace jinak může dojít k selhání. Chyby k uvolnění značky řady způsobí, že nevrácenou pamětí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pMarkerSeries`  
 Adresa poskytovatele objektová proměnná. Adresa nesmí být NULL, proměnná může mít žádnou hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při řady značky úspěšně vydání nebo kód chyby v případě, že existuje byly všechny chyby. Makra úspěšné nebo NEÚSPĚŠNÉ použijte ke kontrole chybový stav.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)