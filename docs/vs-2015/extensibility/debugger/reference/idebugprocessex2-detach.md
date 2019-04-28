---
title: IDebugProcessEx2::Detach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcessEx2::Detach
helpviewer_keywords:
- IDebugProcessEx2::Detach method
ms.assetid: 66d54c2c-9302-47c8-9975-f30ed988ab29
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b79f1f80f9b6849c37fc9b6c4c8669f1397f0227
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62538145"
---
# <a name="idebugprocessex2detach"></a>IDebugProcessEx2::Detach
Tato metoda informuje proces relace je již ladění procesu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Detach( 
   IDebugSession2* pSession
);
```

```csharp
int Detach(
   IDebugSession2 pSession
);
```

#### <a name="parameters"></a>Parametry
 `pSession`

 [in] Hodnota, která jednoznačně identifikuje relace se odpojit od tohoto procesu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Předané rozhraní `pSession` je považován pouze do souboru cookie, hodnotu, která jednoznačně identifikuje správce ladění relace, která původně připojen k tomuto procesu; žádný z metod na zadané rozhraní není funkční.

## <a name="see-also"></a>Viz také
- [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)