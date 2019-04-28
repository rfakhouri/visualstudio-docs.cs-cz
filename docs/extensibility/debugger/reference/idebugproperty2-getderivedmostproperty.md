---
title: IDebugProperty2::GetDerivedMostProperty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetDerivedMostProperty
helpviewer_keywords:
- IDebugProperty2::GetDerivedMostProperty
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1227cb697dc78a8833e304d775fb4b1af85a2a69
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916629"
---
# <a name="idebugproperty2getderivedmostproperty"></a>IDebugProperty2::GetDerivedMostProperty
Získá vlastnost nejvíce odvozené vlastnosti.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDerivedMostProperty ( 
   IDebugProperty2** ppDerivedMost
);
```

```csharp
int GetDerivedMostProperty ( 
   out IDebugProperty2 ppDerivedMost
);
```

#### <a name="parameters"></a>Parametry
 `ppDerivedMost`

 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který reprezentuje vlastnost nejvíce odvozené.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `S_GETDERIVEDMOST_NO_DERIVED_MOST` Pokud není žádná vlastnost odvozené většinu k načtení.

## <a name="remarks"></a>Poznámky
 Například, pokud je tato vlastnost popisuje objekt, který implementuje `ClassRoot` , ale která je ve skutečnosti instance `ClassDerived` , která je odvozena od `ClassRoot`, pak tato metoda vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objektu popisující `ClassDerived` objektu.

## <a name="see-also"></a>Viz také
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)