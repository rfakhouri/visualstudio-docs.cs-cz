---
title: BUILT_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BUILT_TYPE
helpviewer_keywords:
- BUILT_TYPE structure
ms.assetid: cc02c32c-0f65-4210-ad25-a9b1899066e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1a1ecf55b017319850f97c23d926a650c7e01680
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615346"
---
# <a name="builttype"></a>BUILT_TYPE
Tato struktura Určuje informace o typ pole z metadat.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagTYPE_BUILT {
    ULONG32      ulAppDomainID;
    GUID         guidModule;
    IDebugField* pUnderlyingField;
} BUILT_TYPE;
```

```csharp
public struct BUILT_TYPE {
    public uint        ulAppDomainID;
    public Guid        guidModule;
    public IDebugField pUnderlyingField;
};
```

## <a name="members"></a>Členové
`ulAppDomainID`\
ID aplikace, ze kterého přišel symbolu. Slouží k jednoznačné identifikaci instance aplikace.

`guidModule`\
Identifikátor GUID modulu, který obsahuje toto pole.

`pUnderlyingField`\
[IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt identifikuje základní pole přidružené k této vytvořené pole.

## <a name="remarks"></a>Poznámky
Tato struktura se zobrazí jako součást sjednocení v [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) strukturu, kdy `dwKind` pole `TYPE_INFO` struktura je nastavena na `TYPE_KIND_BUILT` (hodnotu z [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) výčet).

## <a name="requirements"></a>Požadavky
Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
