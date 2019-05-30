---
title: PARSEFLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PARSEFLAGS
helpviewer_keywords:
- PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6123c6438defff596351fff3d1ba31ea52a19f28
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349937"
---
# <a name="parseflags"></a>PARSEFLAGS
Určuje, jak analyzovat výrazu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_PARSEFLAGS { 
   PARSE_EXPRESSION            = 0x0001,
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000
};
typedef DWORD PARSEFLAGS;
```

```csharp
public enum enum_PARSEFLAGS { 
   PARSE_EXPRESSION            = 0x0001,
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000
};
```

## <a name="fields"></a>Pole
 `PARSE_EXPRESSION`\
 Označuje, že výraz není příkaz.

 `PARSE_FUNCTION_AS_ADDRESS`\
 Označuje, že výraz má být analyzován (a později vyhodnoceny) jako adresu.

 `PARSE_DESIGN_TIME_EXPR_EVAL`\
 Označuje, že v době návrhu je analyzován výrazu (to znamená, když je Návrhář otevřený).

## <a name="remarks"></a>Poznámky
 Předán jako parametr [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) a [analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) metody.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)
- [Parse](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)