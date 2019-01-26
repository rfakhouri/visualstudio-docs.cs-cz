---
title: Cvinitprovider – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvInitProvider
helpviewer_keywords:
- CvInitProvider method
ms.assetid: ba1863ad-e35f-4d34-a2f2-5e68957d1915
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2fed378aad3a988daa532bb22c0dfd6cb3cbfd2f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923227"
---
# <a name="cvinitprovider-function"></a>Cvinitprovider – funkce
Inicializuje poskytovatele značek. Musí být volána před všechny ostatní funkce sada Vizualizátor souběžnosti SDK.  
  
## <a name="syntax"></a>Syntaxe  
  
```C  
HRESULT CvInitProvider(  
   _In_ const GUID* pGuid,  
   _Out_ PCV_PROVIDER* ppProvider  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pGuid`  
 Identifikátor guid zprostředkovatele. Nemůže mít hodnotu NULL.  
  
 `ppProvider`  
 Adresa proměnné výstup, který bude uložený kontext zprostředkovatele. Nemůže mít hodnotu NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při zprostředkovatel úspěšně inicializován nebo kód chyby v případě, že existuje byly všechny chyby. Použití makra SUCCEEDED nebo FAILED zkontrolujte chybovou podmínku.  
  
## <a name="requirements"></a>Požadavky  
 **Header:** *cvmarkers.h*  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)