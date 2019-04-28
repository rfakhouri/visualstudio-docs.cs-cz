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
ms.openlocfilehash: 09f0438bed235729d390b784725b89abec201c7f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924767"
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

#### <a name="parameters"></a>Parametry
ulAppDomainID ID aplikace, ze kterého přišel symbolu. Slouží k jednoznačné identifikaci instance aplikace.

guidModule GUID modulu, který obsahuje toto pole.

pUnderlyingField [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt identifikuje základní pole přidružené k této vytvořené pole.

## <a name="remarks"></a>Poznámky
Tato struktura se zobrazí jako součást sjednocení v [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) strukturu, kdy `dwKind` pole `TYPE_INFO` struktura je nastavena na `TYPE_KIND_BUILT` (hodnotu z [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) výčet).

## <a name="requirements"></a>Požadavky
Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
