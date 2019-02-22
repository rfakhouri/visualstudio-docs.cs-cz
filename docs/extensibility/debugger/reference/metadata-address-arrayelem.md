---
title: METADATA_ADDRESS_ARRAYELEM | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- METADATA_ADDRESS_ARRAYELEM
helpviewer_keywords:
- METADATA_ADDRESS_ARRAYELEM structure
ms.assetid: 24321be5-7c17-4038-82a1-c20a2b68ff3c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b7cfd9204dfbcc2254da6a4539e6b18d90c156c4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56632794"
---
# <a name="metadataaddressarrayelem"></a>METADATA_ADDRESS_ARRAYELEM
Tato struktura reprezentuje element pole v rámci pole.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagMETADATA_ADDRESS_ARRAYELEM {
    _mdToken tokMethod;
    DWORD    dwIndex;
} METADATA_ADDRESS_ARRAYELEM;
```

```csharp
public struct METADATA_ADDRESS_ARRAYELEM {
    public int  tokMethod;
    public uint dwIndex;
}
```

## <a name="terms"></a>Podmínky
tokMethod  
ID pole tento element je součástí.

[C++] `_mdToken` je `typedef` pro 32bitovou verzi `int`.

dwIndex  
Index tohoto prvku v poli.

## <a name="remarks"></a>Poznámky
Tato struktura je součástí sjednocení v [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) strukturu, kdy `dwKind` pole `DEBUG_ADDRESS_UNION` struktura je nastavena na `ADDRESS_KIND_ARRAYELEM` (hodnotu z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet).

## <a name="requirements"></a>Požadavky
Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)  
[DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)  
[ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)
