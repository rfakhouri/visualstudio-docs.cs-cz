---
title: CONTEXT_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CONTEXT_INFO
helpviewer_keywords:
- CONTEXT_INFO structure
ms.assetid: 6b513f4e-e7b0-4969-adf0-2205ccc1e09b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9a162858431f319e4d56667c2c85b7b53d1d86ab
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316025"
---
# <a name="contextinfo"></a>CONTEXT_INFO
Tato struktura popisuje místní paměti nebo kontext kódu.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagCONTEXT_INFO {
    CONTEXT_INFO_FIELDS dwFields;
    BSTR                bstrModuleUrl;
    BSTR                bstrFunction;
    TEXT_POSITION       posFunctionOffset;
    BSTR                bstrAddress;
    BSTR                bstrAddressOffset;
    BSTR                bstrAddressAbsolute;
} CONTEXT_INFO;
```

```csharp
public struct CONTEXT_INFO {
    public uint          dwFields;
    public string        bstrModuleUrl;
    public string        bstrFunction;
    public TEXT_POSITION posFunctionOffset;
    public string        bstrAddress;
    public string        bstrAddressOffset;
    public string        bstrAddressAbsolute;
};
```

## <a name="members"></a>Členové
dwFields  
Kombinace příznaků z mu [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) výčet, který určuje, která pole jsou vyplněna<strong>.</strong>

bstrModuleUrl  
Název modulu, ve kterém se nachází kontextu.

bstrFunction  
Název funkce, kde se nachází kontextu.

posFunctionOffset  
A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) strukturu, která identifikuje posun řádku a sloupci funkce přidružený kód kontextu.

bstrAddress  
Adresa v kódu, kde se nachází daném kontextu.

bstrAddressOffset  
Posun adresy v kódu, kde se nachází daném kontextu.

bstrAddressAbsolute  
Absolutní adresa v paměti, kde se nachází daném kontextu.

## <a name="remarks"></a>Poznámky
Tato struktura je vrácená z volání [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) metody.

Typickým použitím tato struktura je v podporu **paměti** okno ladění.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)  
[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)  
[CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)  
[TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)
