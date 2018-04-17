---
title: Cvcreatedefaultmarkerseriesofdefaultprovider – funkce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvCreateDefaultMarkerSeriesOfDefaultProvider
helpviewer_keywords:
- CvCreateDefaultMarkerSeriesOfDefaultProvider method
ms.assetid: 24eb80f8-8fca-4c47-93b5-bb1eb8ffdffd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d7b04dcd76eea45264257fca354f321493afed0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="cvcreatedefaultmarkerseriesofdefaultprovider-function"></a>CvCreateDefaultMarkerSeriesOfDefaultProvider – funkce
Vytvoří výchozí značky řadu výchozího zprostředkovatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CvCreateDefaultMarkerSeriesOfDefaultProvider(  
   _Out_ PCV_PROVIDER* ppProvider,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppProvider`  
 Adresa poskytovatele objektová proměnná. Adresa nesmí být NULL, proměnná může mít žádnou hodnotu.  
  
 `ppMarkerSeries`  
 Adresa značky řady objektová proměnná. Adresa nesmí být NULL, proměnná může mít žádnou hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při řady zprostředkovatele a značky jsou úspěšně vytvořeny nebo kód chyby v případě, že existuje byly všechny chyby. Makra úspěšné nebo NEÚSPĚŠNÉ použijte ke kontrole chybový stav.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)