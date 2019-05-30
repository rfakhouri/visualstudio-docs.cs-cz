---
title: CONTEXT_COMPARE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONTEXT_COMPARE
helpviewer_keywords:
- CONTEXT_COMPARE enumeration
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 28e81e8247e0ab7a7b2e972209805c8bcff053a7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346403"
---
# <a name="contextcompare"></a>CONTEXT_COMPARE
Určuje kritéria pro porovnání dvou kontextů paměti.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_CONTEXT_COMPARE {
    CONTEXT_EQUAL                 = 0x0001,
    CONTEXT_LESS_THAN             = 0x0002,
    CONTEXT_GREATER_THAN          = 0x0003,
    CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,
    CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,
    CONTEXT_SAME_SCOPE            = 0x0006,
    CONTEXT_SAME_FUNCTION         = 0x0007,
    CONTEXT_SAME_MODULE           = 0x0008,
    CONTEXT_SAME_PROCESS          = 0x0009
};
typedef DWORD CONTEXT_COMPARE;
```

```csharp
public enum enum_CONTEXT_COMPARE {
    CONTEXT_EQUAL                 = 0x0001,
    CONTEXT_LESS_THAN             = 0x0002,
    CONTEXT_GREATER_THAN          = 0x0003,
    CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,
    CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,
    CONTEXT_SAME_SCOPE            = 0x0006,
    CONTEXT_SAME_FUNCTION         = 0x0007,
    CONTEXT_SAME_MODULE           = 0x0008,
    CONTEXT_SAME_PROCESS          = 0x0009
};
```

## <a name="fields"></a>Pole
`CONTEXT_EQUAL`\
Vyhledá první kontext paměti v seznamu, který je roven cílový kontext paměti.

`CONTEXT_LESS_THAN`\
Vyhledá první kontext paměti v seznamu, která je menší než cílový kontext paměti.

`CONTEXT_GREATER_THAN`\
Vyhledá první kontext paměti v seznamu, která je větší než cílový kontext paměti.

`CONTEXT_LESS_THAN_OR_EQUAL`\
Vyhledá první kontext paměti v seznamu, která je menší než nebo rovna hodnotě cílový kontext paměti.

`CONTEXT_GREATER_THAN_OR_EQUAL`\
Najdete první paměťové oblasti v seznamu, který je větší než nebo rovna hodnotě cílový kontext paměti.

`CONTEXT_SAME_SCOPE`\
Vyhledá první kontext paměti v seznamu, který je ve stejném oboru jako cílový kontext paměti.

`CONTEXT_SAME_FUNCTION`\
Najdete první paměťové oblasti v seznamu, který je ve stejné funkci jako cílový obor paměti.

`CONTEXT_SAME_MODULE`\
Vyhledá první kontext paměti v seznamu, který je ve stejném modulu jako cílový kontext paměti.

`CONTEXT_SAME_PROCESS`\
Vyhledá první kontext paměti v seznamu, který je ve stejném procesu jako cílový kontext paměti.

## <a name="remarks"></a>Poznámky
Předán jako argument [porovnání](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md) metody.

Tyto hodnoty se používají k vyhledání prvního kontextu paměti v seznamu, který splňuje zadané porovnávací kritéria. Kontext paměti je uveden seznam kontexty paměti se porovnat proti prostřednictvím `IDebugMemoryContext2::Compare` metody. První kontext paměti v seznamu, pro který je operátor porovnání `true` je poté vrácen.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)
