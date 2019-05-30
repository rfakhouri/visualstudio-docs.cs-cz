---
title: EVALFLAGS90 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 24afc4456570ff0c3e5dc1eb56789984bf18ac58
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337834"
---
# <a name="evalflags90"></a>EVALFLAGS90
Vytvoří výčet platné hodnoty pro příznaky, které řídí vyhodnocení výrazu. Tento výčet rozšiřuje [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_EVALFLAGS90
{
    // VS 8.0 values
    EVAL90_RETURNVALUE                 = 0x0002,
    EVAL90_NOSIDEEFFECTS               = 0x0004,
    EVAL90_ALLOWBPS                    = 0x0008,
    EVAL90_ALLOWERRORREPORT            = 0x0010,
    EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,
    EVAL90_NOFUNCEVAL                  = 0x0080,
    EVAL90_NOEVENTS                    = 0x1000,
    EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,
    EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,

    // Values added in VS 9.0
    EVAL90_FORCE_EVALUATION_NOW        = 0x8000
};
typedef DWORD EVALFLAGS90;
```

```csharp
public enum enum_EVALFLAGS90
{
    // VS 8.0 values
    EVAL90_RETURNVALUE                 = 0x0002,
    EVAL90_NOSIDEEFFECTS               = 0x0004,
    EVAL90_ALLOWBPS                    = 0x0008,
    EVAL90_ALLOWERRORREPORT            = 0x0010,
    EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,
    EVAL90_NOFUNCEVAL                  = 0x0080,
    EVAL90_NOEVENTS                    = 0x1000,
    EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,
    EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,

    // Values added in VS 9.0
    EVAL90_FORCE_EVALUATION_NOW        = 0x8000
};
```

## <a name="fields"></a>Pole
`EVAL90_RETURNVALUE`\
Určuje, že návratová hodnota, pokud existuje, vyhodnocen.

`EVAL90_NOSIDEEFFECTS`\
Určuje, že nebudou povoleny vedlejší účinky.

`EVAL90_ALLOWBPS`\
Určuje zastavení zarážky.

`EVAL90_ALLOWERRORREPORT`\
Určuje tuto chybu generování sestav k hostiteli mají být povolena. Používá se především pro vyhodnocení výrazu ve skriptu v aplikaci Internet Explorer.

`EVAL90_FUNCTION_AS_ADDRESS`\
Funkce sil má být vyhodnocen jako adresy, namísto volání funkce.

`EVAL90_NOFUNCEVAL`\
Zabraňuje vyhodnocení funkce. Představme si třeba, `int` token ve výrazu `myExpression(int) + 10`. Tato funkce může být správně vyhodnocen jako adresa, ale ne jako hodnotu.

`EVAL90_NOEVENTS`\
Příznak označující, že správce ladění relace (SDM) nebo integrovaném vývojovém prostředí by se neměly posílat události, ke kterým dochází při vyhodnocení výrazu.

`EVAL90_DESIGN_TIME_EXPR_EVAL`\
Umožňuje vyhodnocování výrazu v době návrhu.

`EVAL90_ALLOW_IMPLICIT_VARS`\
Umožňuje implicitní vytváření proměnných.

`EVAL90_FORCE_EVALUATION_NOW`\
Vyhodnocení vynutí okamžité. To je užitečné při obsluze žádosti, jako je například požadavek uživatele.

## <a name="requirements"></a>Požadavky
Záhlaví: Msdbg90.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
