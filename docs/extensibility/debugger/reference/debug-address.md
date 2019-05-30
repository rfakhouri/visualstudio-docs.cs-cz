---
title: DEBUG_ADDRESS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_ADDRESS
helpviewer_keywords:
- DEBUG_ADDRESS structure
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: dc25fb53db918486029e931a06a9e2de37f81c5a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346311"
---
# <a name="debugaddress"></a>DEBUG_ADDRESS
Tato struktura představuje adresu.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagDEBUG_ADDRESS {
    ULONG32             ulAppDomainID;
    GUID                guidModule;
    _mdToken            tokClass;
    DEBUG_ADDRESS_UNION addr;
} DEBUG_ADDRESS;
```

```csharp
public struct DEBUG_ADDRESS {
    public uint                ulAppDomainID;
    public Guid                guidModule;
    public int                 tokClass;
    public DEBUG_ADDRESS_UNION addr;
}
```

## <a name="members"></a>Členové
`ulAppDomainID`\
ID procesu.

`guidModule`\
Identifikátor GUID modulu, který obsahuje tuto adresu.

`tokClass`\
Token třídy nebo typu tuto adresu.

> [!NOTE]
> Tato hodnota je specifické pro zprostředkovatele symbolů a proto nemá žádný význam obecné jiných než jako identifikátor pro typ třídy.

`addr`\
A [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) struktura, která obsahuje sjednocení, struktur, které popisují typy jednotlivých adres. Hodnota `addr`.`dwKind` pochází z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet, který vysvětluje, jak interpretovat sjednocení.

## <a name="remarks"></a>Poznámky
Tato struktura je předán [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) metoda být vyplněna.

**Upozornění [C++ pouze]**

Pokud `addr.dwKind` je `ADDRESS_KIND_METADATA_LOCAL` a pokud `addr.addr.addrLocal.pLocal` není hodnotou null, pak je nutné volat `Release` token ukazatele:

```
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL && addr.addr.addrLocal.pLocal != NULL)
{
    addr.addr.addrLocal.pLocal->Release();
}
```

## <a name="requirements"></a>Požadavky
Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
- [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)
