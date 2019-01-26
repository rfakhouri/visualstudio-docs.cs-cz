---
title: Cvcreatemarkerserieswithcodepagea – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords:
- CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 410e23163d2d12ac141aecdc7d7f65036ff26406
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54942071"
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>Cvcreatemarkerserieswithcodepagea – funkce
Vytvoří značku řady pro daného poskytovatele a zadanou znakovou stránku. Tato funkce slouží k určení znakovou stránku explicitně pro textu zapsaného funkce rozhraní API ANSI značky. Nastavení znakové stránky může být užitečné v případě trasování je zachycena a potom analyzovány na odlišných počítačích s různými národní prostředí nebo jazyky. Ve výchozím nastavení se používá znakovou stránku vrácená funkcí GetACP().  
  
## <a name="syntax"></a>Syntaxe  
  
```C  
HRESULT CvCreateMarkerSeriesWithCodePageA(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ LPCSTR pSeriesName,  
   _In_ UINT nTextCodePage,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProvider`  
 Cvinitprovider – dříve inicializován objekt zprostředkovatele. Nemůže mít hodnotu NULL.  
  
 `pSeriesName`  
 Název značky řady. Nemůže mít hodnotu NULL, ale je povolen prázdný řetězec.  
  
 `nTextCodePage`  
 Platný znakovou stránku.  
  
 `ppMarkerSeries`  
 Adresa výstupní proměnné, která bude ukládat značky řady kontextu. Nemůže mít hodnotu NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při úspěšném vytvoření značky řady nebo kód chyby v případě, že existuje byly všechny chyby. Použití makra SUCCEEDED nebo FAILED zkontrolujte chybovou podmínku.  
  
## <a name="requirements"></a>Požadavky  
 **Header:** *cvmarkers.h*  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)