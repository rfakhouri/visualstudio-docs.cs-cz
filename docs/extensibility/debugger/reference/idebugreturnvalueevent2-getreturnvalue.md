---
title: IDebugReturnValueEvent2::GetReturnValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReturnValueEvent2::GetReturnValue
helpviewer_keywords:
- IDebugReturnValueEvent2::GetReturnValue
ms.assetid: 86c50d5a-6df6-4798-818a-c587a8741f90
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 76d129d433f43b9264dc7262841d9b84c4d729c2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916285"
---
# <a name="idebugreturnvalueevent2getreturnvalue"></a>IDebugReturnValueEvent2::GetReturnValue
Získá hodnotu vrácenou v krokování z celkového počtu nebo funkci.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetReturnValue ( 
   IDebugProperty2** ppReturnValue
);
```

```csharp
int GetReturnValue ( 
   out IDebugProperty2 ppReturnValue
);
```

#### <a name="parameters"></a>Parametry
 `ppReturnValue`

 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který představuje hodnotu, která se má načíst.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugReturnValueEvent2](../../../extensibility/debugger/reference/idebugreturnvalueevent2.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)