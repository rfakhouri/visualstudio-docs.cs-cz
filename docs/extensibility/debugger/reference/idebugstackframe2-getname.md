---
title: IDebugStackFrame2::GetName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetName
helpviewer_keywords:
- IDebugStackFrame2::GetName
ms.assetid: 069d4f96-363f-404e-9c89-5318c4c9821b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 076e744be4e97cc8c58d5b5f7578f1701f39d711
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714255"
---
# <a name="idebugstackframe2getname"></a>IDebugStackFrame2::GetName
Získá název rámce zásobníku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetName ( 
   BSTR* pbstrName
);
```

```csharp
int GetName ( 
   out string pbstrName
);
```

#### <a name="parameters"></a>Parametry
 `pbstrName`

 [out] Vrátí název rámce zásobníku.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Název bloku zásobníku je obvykle název metody, které se spouští.

## <a name="see-also"></a>Viz také
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)