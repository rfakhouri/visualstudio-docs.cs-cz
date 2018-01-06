---
title: "Cvcreatemarkerserieswithcodepagea – funkce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords: CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6e435e702b25bd3abaacd4a789d635901617a611
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>CvCreateMarkerSeriesWithCodePageA – funkce
Vytvoří řady značky pro daného zprostředkovatele a zadány znaková stránka. Tato funkce slouží k určení kódové stránky explicitně pro text naprogramovaný funkce rozhraní API ANSI značky. Nastavení znakové stránky může být užitečné v případě, že bude zachycen a potom analyzovat na různé počítače s jinou národní prostředí nebo jazyky trasování. Ve výchozím nastavení se používá znaková stránka vrácené funkcí GetACP().  
  
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