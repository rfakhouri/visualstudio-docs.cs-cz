---
title: IDiaStackWalkHelper::put_registerValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::put_registerValue method
ms.assetid: 8f02ce54-ef59-455f-8aa6-dc26761c7aff
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b3d0cdcd31419f23a69eea019b38304eb6feba8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956943"
---
# <a name="idiastackwalkhelperputregistervalue"></a>IDiaStackWalkHelper::put_registerValue
Nastaví hodnotu registru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT put_registerValue (   
   DWORD     index,  
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `index`  
 [in] Hodnota z [cv_hreg_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md) výčet určující k zápisu do registru.  
  
 `NewVal`  
 [in] Nové hodnoty registru.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Bez ohledu na velikost hodnota by měla implementace ukládání co do registru obvykle obsahuje pouze. Například 8bitový registr, by uchovával jen nejnižší 8 bitů předané hodnoty.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV_HREG_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md)