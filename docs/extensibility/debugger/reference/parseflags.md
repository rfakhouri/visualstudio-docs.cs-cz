---
title: PARSEFLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PARSEFLAGS
helpviewer_keywords:
- PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e5d298add846a7f3b7baf566f3c31e16c68b8dc5
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460834"
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