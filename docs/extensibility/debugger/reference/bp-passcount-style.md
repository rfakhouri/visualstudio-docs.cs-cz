---
title: BP_PASSCOUNT_STYLE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_PASSCOUNT_STYLE
helpviewer_keywords:
- BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 373478bfcdac1ea8c34bc96c873df003e490dac1
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315233"
---
# <a name="bppasscountstyle"></a>BP_PASSCOUNT_STYLE
Určuje podmínku, počet průchodu zarážky, který způsobí, že zarážka má provést, přidružené.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BP_PASSCOUNT_STYLE {
    BP_PASSCOUNT_NONE             = 0x0000,
    BP_PASSCOUNT_EQUAL            = 0x0001,
    BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,
    BP_PASSCOUNT_MOD              = 0x0003
};
typedef DWORD BP_PASSCOUNT_STYLE;
```

```csharp
public enum enum_BP_PASSCOUNT_STYLE {
    BP_PASSCOUNT_NONE             = 0x0000,
    BP_PASSCOUNT_EQUAL            = 0x0001,
    BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,
    BP_PASSCOUNT_MOD              = 0x0003
};
```

## <a name="members"></a>Členové
BP_PASSCOUNT_NONE  
Určuje styl počet pass bez zarážek.

BP_PASSCOUNT_EQUAL  
Nastaví styl počet průchodu zarážky rovno. Zarážka je vyvoláno, pokud počet pokusů, které je zarážka dosažena rovná počtu průchodu.

BP_PASSCOUNT_EQUAL_OR_GREATER  
Nastaví styl počet průchodu zarážky na stejné nebo větší. Zarážka aktivuje se v případě, že počet pokusů, které je zarážka dosažena je roven nebo větší než počet pass.

BP_PASSCOUNT_MOD  
Určuje, počet průchodů modulo. Například, pokud je počet průchodu typu `BP_PASSCOUNT_MOD` a je hodnota počtu průchodu 4, aktivována zarážka pokaždé, když je počet průchodů násobek čísla 4.

## <a name="remarks"></a>Poznámky
Používá pro `stylePassCount` člena [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) struktura, která je členem skupiny [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) a [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)  
[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)  
[BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
