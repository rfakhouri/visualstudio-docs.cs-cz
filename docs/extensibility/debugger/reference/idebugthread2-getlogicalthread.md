---
title: IDebugThread2::GetLogicalThread | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::GetLogicalThread
helpviewer_keywords:
- IDebugThread2::GetLogicalThread
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9e57d3deac01b00f1f332b34075d74f6402235f4
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65224029"
---
# <a name="idebugthread2getlogicalthread"></a>IDebugThread2::GetLogicalThread
Ladicí stroj neimplementují této metody.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetLogicalThread( 
   IDebugStackFrame2*     pStackFrame,
   IDebugLogicalThread2** ppLogicalThread
);
```

```csharp
int GetLogicalThread( 
   IDebugStackFrame2        pStackFrame,
   out IDebugLogicalThread2 ppLogicalThread
);
```

## <a name="parameters"></a>Parametry
 `pStackFrame`\

 [in] [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) objekt představující rámec zásobníku.

 `ppLogicalThread`\

 [out] Vrátí `IDebugLogicalThread2` rozhraní, které představuje přidružené logické vlákno. Implementace modulu ladění by měl nastavíte na hodnotu null.

## <a name="return-value"></a>Návratová hodnota
 Ladění vždy návratový stroj implementace `E_NOTIMPL`.

## <a name="see-also"></a>Viz také:
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)