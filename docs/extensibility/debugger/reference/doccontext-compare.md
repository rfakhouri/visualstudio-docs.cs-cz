---
title: DOCCONTEXT_COMPARE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f31b33eeb782e71a87103d26a3bb78175611644e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66318136"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
Určuje kritéria pro porovnání dvou kontextů dokumentu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_DOCCONTEXT_COMPARE {
    DOCCONTEXT_EQUAL         = 0x0001,
    DOCCONTEXT_LESS_THAN     = 0x0002,
    DOCCONTEXT_GREATER_THAN  = 0x0003,
    DOCCONTEXT_SAME_DOCUMENT = 0x0004
};
typedef DWORD DOCCONTEXT_COMPARE;
```

```csharp
enum enum_DOCCONTEXT_COMPARE {
    DOCCONTEXT_EQUAL         = 0x0001,
    DOCCONTEXT_LESS_THAN     = 0x0002,
    DOCCONTEXT_GREATER_THAN  = 0x0003,
    DOCCONTEXT_SAME_DOCUMENT = 0x0004
};
```

## <a name="fields"></a>Pole
`DOCCONTEXT_EQUAL`\
Vyhledá první kontext dokumentu v seznamu, který je roven cílový kontext dokumentu.

`DOCCONTEXT_LESS_THAN`\
Vyhledá první kontext dokumentu v seznamu, která je menší než cílový kontext dokumentu.

`DOCCONTEXT_GREATER_THAN`\
Vyhledá první kontext dokumentu v seznamu, který je větší než cílový kontext dokumentu.

`DOCCONTEXT_SAME_DOCUMENT`\
Vyhledá první kontext dokumentu v seznamu, který je ve stejném dokumentu jako cílový kontext dokumentu.

## <a name="remarks"></a>Poznámky
Předán jako argument [porovnání](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) metody.

Tyto hodnoty se používají k určení porovnání kritérií pro hledání v seznamu první kontext dokumentu. Kontext dokumentu je uveden seznam kontexty dokumentu se porovnat proti prostřednictvím `IDebugDocumentContext2::Compare` metody. První kontext dokumentu v seznamu, pro který je operátor porovnání `true` je poté vrácen.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)
