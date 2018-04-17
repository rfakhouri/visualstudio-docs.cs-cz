---
title: Cvcreatemarkerserieswithcodepagea – funkce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords:
- CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 94c9e1c6e0fdcefc542784f567798ec372eee90a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>CvCreateMarkerSeriesWithCodePageA – funkce
Vytvoří řady značky daného poskytovatele a zadanou znakovou stránku. Tato funkce slouží k určení kódové stránky explicitně pro text naprogramovaný funkce rozhraní API ANSI značky. Nastavení znakové stránky může být užitečné v případě, že bude zachycen a potom analyzovat na různé počítače s jinou národní prostředí nebo jazyky trasování. Ve výchozím nastavení se používá znaková stránka vrácené funkcí GetACP().  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CvCreateMarkerSeriesWithCodePageA(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ LPCSTR pSeriesName,  
   _In_ UINT nTextCodePage,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProvider`  
 Objekt zprostředkovatele dříve iniciovány cvinitprovider –. Nemůže mít hodnotu NULL.  
  
 `pSeriesName`  
 Název řady značky. Nemůže mít hodnotu NULL, ale je povolen prázdný řetězec.  
  
 `nTextCodePage`  
 Neplatná znaková stránka.  
  
 `ppMarkerSeries`  
 Adresa proměnná výstup, který uloží kontextu řady značky. Nemůže mít hodnotu NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při řady značky se úspěšně vytvořil nebo kód chyby v případě, že existuje byly všechny chyby. Makra úspěšné nebo NEÚSPĚŠNÉ použijte ke kontrole chybový stav.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)