---
title: Cvreleasemarkerseries – funkce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca6f11d7c1d89a9ba5b484bf2d3bb1b1839b4822
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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