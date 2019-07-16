---
title: Cvinitprovider – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- cvmarkers/CvInitProvider
helpviewer_keywords:
- CvInitProvider method
ms.assetid: ba1863ad-e35f-4d34-a2f2-5e68957d1915
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a5a8a9e70c85563e95037c754c59b6077ed21f28
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68188801"
---
# <a name="cvinitprovider-function"></a>CvInitProvider – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Inicializuje poskytovatele značek. Musí být volána před všechny ostatní funkce sada Vizualizátor souběžnosti SDK.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)
