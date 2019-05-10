---
title: UNMANAGED_ADDRESS_PHYSICAL | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UNMANAGED_ADDRESS_PHYSICAL
helpviewer_keywords:
- UNMANAGED_ADDRESS_PHYSICAL structure
ms.assetid: fed09686-caa6-4efc-851e-a0432019e9d0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a588a0e2438d1f95f8114e81c58330dd6f0ccd2b
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458439"
---
# <a name="unmanagedaddressphysical"></a>UNMANAGED_ADDRESS_PHYSICAL
Tato struktura představuje fyzickou adresu.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagUNMANAGED_ADDRESS_PHYSICAL {
   ULONGLONG offset;
} UNMANAGED_ADDRESS_PHYSICAL;
```

```csharp
public struct UNMANAGED_ADDRESS_PHYSICAL {
   public ulong offset;
}
```

## <a name="members"></a>Členové
 `offset`\
 Posun 64-bit na fyzický adresní prostor.

## <a name="remarks"></a>Poznámky
 Tato struktura je součástí sjednocení v [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) strukturu, kdy `dwKind` pole `DEBUG_ADDRESS_UNION` struktura je nastavena na `ADDRESS_KIND_UNMANAGED_PHYSICAL` (hodnotu z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet).

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)