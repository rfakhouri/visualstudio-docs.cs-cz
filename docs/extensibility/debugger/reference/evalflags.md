---
title: EVALFLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2a56f7d5fe4741fa887814691eddcf8df93030cd
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337884"
---
# <a name="evalflags"></a>EVALFLAGS
Určuje příznaky, které řídí vyhodnocení výrazu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_EVALFLAGS {
    EVAL_RETURNVALUE = 0x0002,
    EVAL_NOSIDEEFFECTS = 0x0004,
    EVAL_ALLOWBPS = 0x0008,
    EVAL_ALLOWERRORREPORT = 0x0010,
    EVAL_FUNCTION_AS_ADDRESS = 0x0040,
    EVAL_NOFUNCEVAL = 0x0080,
    EVAL_NOEVENTS = 0x1000
};
typedef DWORD EVALFLAGS;
```

```csharp
public enum enum_EVALFLAGS {
    EVAL_RETURNVALUE = 0x0002,
    EVAL_NOSIDEEFFECTS = 0x0004,
    EVAL_ALLOWBPS = 0x0008,
    EVAL_ALLOWERRORREPORT = 0x0010,
    EVAL_FUNCTION_AS_ADDRESS = 0x0040,
    EVAL_NOFUNCEVAL = 0x0080,
    EVAL_NOEVENTS = 0x1000
}
```

## <a name="fields"></a>Pole
`EVAL_RETURNVALUE`\
Určuje, že návratová hodnota, pokud existuje, vyhodnocen.

`EVAL_NOSIDEEFFECTS`\
Určuje, že nebudou povoleny vedlejší účinky.

`EVAL_ALLOWBPS`\
Určuje zastavení zarážky.

`EVAL_ALLOWERRORREPORT`\
Určuje zpráv o chybách k hostiteli mají být povolena. Používá se především pro vyhodnocení výrazu ve skriptu v aplikaci Internet Explorer.

`EVAL_FUNCTION_AS_ADDRESS`\
Funkce sil má být vyhodnocen jako adresy, namísto volání funkce.

`EVAL_NOFUNCEVAL`\
Zabraňuje vyhodnocení funkce. Představme si třeba, `int` token ve výrazu `myExpression(int) + 10`. Tato funkce může být správně vyhodnocen jako adresa, ale ne jako hodnotu.

`EVAL_NOEVENTS`\
Příznak označující, že správce ladění relace (SDM) nebo integrovaném vývojovém prostředí by se neměly posílat události, ke kterým dochází při vyhodnocení výrazu.

## <a name="remarks"></a>Poznámky
Tyto příznaky jsou předány jako argument [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) a [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) metody.

Tyto příznaky lze kombinovat s bitový operátor OR.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)
