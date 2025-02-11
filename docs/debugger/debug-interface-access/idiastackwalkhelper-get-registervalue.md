---
title: IDiaStackWalkHelper::get_registerValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::get_registerValue method
ms.assetid: 46ac5eee-73a3-44a1-8635-6c58ba193cb6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 275941aaf3a1eb2cab6554b18c6d9aa66605121a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62831829"
---
# <a name="idiastackwalkhelpergetregistervalue"></a>IDiaStackWalkHelper::get_registerValue
Načte hodnotu registru.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_registerValue ( 
   DWORD      index,
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `index`

[in] Hodnota z [cv_hreg_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md) výčet určující, které zaregistrovat k získání hodnoty z.

 `pRetVal`

[out] Vrátí aktuální hodnotu registru.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Bez ohledu na velikost `pRetVal` parametr, implementace by měla být uložena pouze co do registru obvykle obsahuje. Například 8bitový registr obsahuje pouze nejnižší 8 bitů předané hodnoty. Tato hodnota 8 bitů rozbalen do 64 bitů když tato metoda vrátí.

## <a name="see-also"></a>Viz také
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [CV_HREG_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md)