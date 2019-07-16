---
title: Cvcreatemarkerseries – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- cvmarkers/CvCreateMarkerSeriesA
- cvmarkers/CvCreateMarkerSeriesW
helpviewer_keywords:
- CvCreateMarkerSeriesA method
- CvCreateMarkerSeriesW method
ms.assetid: e280530b-137a-43a7-8643-aa514ab86ed7
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6dc4af6ef3b2ffc89ec0e69a6dd63923f5c55ffe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68155537"
---
# <a name="cvcreatemarkerseries-function"></a>CvCreateMarkerSeries – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vytvoří značku řady pro daného zprostředkovatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_Check_return_ HRESULT CvCreateMarkerSeriesW(  
    _In_ PCV_PROVIDER  pProvider,  
    _In_ LPCWSTR pSeriesName,  
    _Out_ PCV_MARKERSERIES* ppMarkerSeries);  
  
_Check_return_ HRESULT CvCreateMarkerSeriesA(  
    _In_ PCV_PROVIDER  pProvider,  
    _In_ LPCSTR pSeriesName,  
    _Out_ PCV_MARKERSERIES* ppMarkerSeries);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProvider`  
 Cvinitprovider – dříve inicializován objekt zprostředkovatele. Nemůže mít hodnotu NULL.  
  
 `pSeriesName`  
 Název značky řady. Nemůže mít hodnotu NULL, ale je povolen prázdný řetězec.  
  
 `ppMarkerSeries`  
 Adresa výstupní proměnné, která bude ukládat značky řady kontextu. Nemůže mít hodnotu NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při úspěšném vytvoření značky řady nebo kód chyby v případě, že existuje byly všechny chyby. Použití makra SUCCEEDED nebo FAILED zkontrolujte chybovou podmínku.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkers.h  
  
 **Unicode:** Cvcreatemarkerseriesw –  
  
 **ANSI:** CvCreateMarkerSeriesA  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)
