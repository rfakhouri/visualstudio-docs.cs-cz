---
title: BP_LOCATION_CODE_STRING | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_STRING
helpviewer_keywords:
- BP_LOCATION_CODE_STRING structure
ms.assetid: a4cd71c6-5052-45fe-907b-ebc6ca1df2e4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0650c7b3c2961531b64539887a1c4c68ac2bc819
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316207"
---
# <a name="bplocationcodestring"></a>BP_LOCATION_CODE_STRING
Používá k nastavení kódu zarážky založené na řetězec, který může uživatel zadat z integrovaného vývojového prostředí (IDE).

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _BP_LOCATION_CODE_STRING {
    BSTR bstrContext;
    BSTR bstrCodeExpr;
} BP_LOCATION_CODE_STRING;
```

## <a name="members"></a>Členové
`bstrContext`  
Kontext zarážky v kódu, obvykle název metody nebo funkce jako zobrazení zásobníku volání.

`bstrCodeExpr`  
Řetězec, který uživatel zadává pro popis kódu zarážku.

## <a name="remarks"></a>Poznámky
Tato struktura je členem skupiny [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktury v rámci sjednocení.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)  
[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)
