---
title: IDebugThread2::Suspend | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::Suspend
helpviewer_keywords:
- IDebugThread2::Suspend
ms.assetid: 1e20be85-aa12-48de-bb83-0bf0976e99ae
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e45cee0acab5fb2b5165e28895ab9a7dcb3ed9c1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56683659"
---
# <a name="idebugthread2suspend"></a>IDebugThread2::Suspend
Pozastaví vlákno.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Suspend ( 
   DWORD *pdwSuspendCount
);
```

```csharp
HRESULT Suspend ( 
   out uint pdwSuspendCount
);
```

#### <a name="parameters"></a>Parametry
 `pdwSuspendCount`

 [out] Vrátí počet pozastavení po provedení této operace pozastavit.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Každé volání této metody zvýší počet pozastavení větší než 0. Zobrazí se tento počet pozastavení v **vlákna** okno ladění.

 Pro každé volání této metody musí být pozdější volání [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md) metody.

## <a name="see-also"></a>Viz také
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)