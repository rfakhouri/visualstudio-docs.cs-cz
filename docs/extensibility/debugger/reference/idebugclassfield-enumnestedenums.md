---
title: IDebugClassField::EnumNestedEnums | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumNestedEnums
helpviewer_keywords:
- IDebugClassField::EnumNestedEnums method
ms.assetid: 90fd0cef-9145-4de6-91d4-6c881df39d6e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 01465a0b921d61a07c4d31c8d4d4ba4b70e5bafd
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66206859"
---
# <a name="idebugclassfieldenumnestedenums"></a>IDebugClassField::EnumNestedEnums
Vytvoří čítač pro vnořené čítačů této třídy.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumNestedEnums(
    IEnumDebugFields** ppEnum
);
```

```csharp
int EnumNestedEnums(
    out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>Parametry
`ppEnum`\
[out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam vnořených výčty. Vrátí hodnotu null, pokud neexistují žádné vnořené výčty.

## <a name="return-value"></a>Návratová hodnota
V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné vnořené enumerátory. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
Každý prvek výčtu je [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) objekt popisující vnořené výčtu.

Deklarované uvnitř třídy výčet je považován za vnořený výčtu. Mějme například:

```
class RootClass {
    enum NestedEnum { EnumValue = 0 }
};
```

`EnumNestedEnums` By metoda vrátit [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt, který obsahuje jeden [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) objekt, který reprezentuje `NestedEnum` výčtu.

## <a name="see-also"></a>Viz také:
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
