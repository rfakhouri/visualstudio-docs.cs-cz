---
title: FRAMEINFO_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FRAMEINFO_FLAGS
helpviewer_keywords:
- FRAMEINFO_FLAGS enumeration
ms.assetid: 41578062-8455-412a-9d8b-1e1e9dc8d52e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 54bb93fa6f88c02731691728bceacdd4a5fe2036
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924199"
---
# <a name="frameinfoflags"></a>FRAMEINFO_FLAGS
Určuje informace, které se mají načíst informace o objektu rámce zásobníku.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_FRAMEINFO_FLAGS {
    FIF_FUNCNAME              = 0x00000001,
    FIF_RETURNTYPE            = 0x00000002,
    FIF_ARGS                  = 0x00000004,
    FIF_LANGUAGE              = 0x00000008,
    FIF_MODULE                = 0x00000010,
    FIF_STACKRANGE            = 0x00000020,
    FIF_FRAME                 = 0x00000040,
    FIF_DEBUGINFO             = 0x00000080,
    FIF_STALECODE             = 0x00000100,
    FIF_ANNOTATEDFRAME        = 0x00000200,
    FIF_DEBUG_MODULEP         = 0x00000400,
    FIF_FUNCNAME_FORMAT       = 0x00001000,
    FIF_FUNCNAME_RETURNTYPE   = 0x00002000,
    FIF_FUNCNAME_ARGS         = 0x00004000,
    FIF_FUNCNAME_LANGUAGE     = 0x00008000,
    FIF_FUNCNAME_MODULE       = 0x00010000,
    FIF_FUNCNAME_LINES        = 0x00020000,
    FIF_FUNCNAME_OFFSET       = 0x00040000,
    FIF_FUNCNAME_ARGS_TYPES   = 0x00100000,
    FIF_FUNCNAME_ARGS_NAMES   = 0x00200000,
    FIF_FUNCNAME_ARGS_VALUES  = 0x00400000,
    FIF_FUNCNAME_ARGS_ALL     = 0x00700000,
    FIF_ARGS_TYPES            = 0x01000000,
    FIF_ARGS_NAMES            = 0x02000000,
    FIF_ARGS_VALUES           = 0x04000000,
    FIF_ARGS_ALL              = 0x07000000,
    FIF_ARGS_NOFORMAT         = 0x08000000,
    FIF_ARGS_NO_FUNC_EVAL     = 0x10000000,
    FIF_FILTER_NON_USER_CODE  = 0x20000000,
    FIF_ARGS_NO_TOSTRING      = 0x40000000,
    FIF_DESIGN_TIME_EXPR_EVAL = 0x80000000
};
typedef DWORD FRAMEINFO_FLAGS;
```

```csharp
public enum enum_FRAMEINFO_FLAGS {
    FIF_FUNCNAME              = 0x00000001,
    FIF_RETURNTYPE            = 0x00000002,
    FIF_ARGS                  = 0x00000004,
    FIF_LANGUAGE              = 0x00000008,
    FIF_MODULE                = 0x00000010,
    FIF_STACKRANGE            = 0x00000020,
    FIF_FRAME                 = 0x00000040,
    FIF_DEBUGINFO             = 0x00000080,
    FIF_STALECODE             = 0x00000100,
    FIF_ANNOTATEDFRAME        = 0x00000200,
    FIF_DEBUG_MODULEP         = 0x00000400,
    FIF_FUNCNAME_FORMAT       = 0x00001000,
    FIF_FUNCNAME_RETURNTYPE   = 0x00002000,
    FIF_FUNCNAME_ARGS         = 0x00004000,
    FIF_FUNCNAME_LANGUAGE     = 0x00008000,
    FIF_FUNCNAME_MODULE       = 0x00010000,
    FIF_FUNCNAME_LINES        = 0x00020000,
    FIF_FUNCNAME_OFFSET       = 0x00040000,
    FIF_FUNCNAME_ARGS_TYPES   = 0x00100000,
    FIF_FUNCNAME_ARGS_NAMES   = 0x00200000,
    FIF_FUNCNAME_ARGS_VALUES  = 0x00400000,
    FIF_FUNCNAME_ARGS_ALL     = 0x00700000,
    FIF_ARGS_TYPES            = 0x01000000,
    FIF_ARGS_NAMES            = 0x02000000,
    FIF_ARGS_VALUES           = 0x04000000,
    FIF_ARGS_ALL              = 0x07000000,
    FIF_ARGS_NOFORMAT         = 0x08000000,
    FIF_ARGS_NO_FUNC_EVAL     = 0x10000000,
    FIF_FILTER_NON_USER_CODE  = 0x20000000,
    FIF_ARGS_NO_TOSTRING      = 0x40000000,
    FIF_DESIGN_TIME_EXPR_EVAL = 0x80000000
};
```

## <a name="members"></a>Členové
FIF_FUNCNAME inicializace/použít `m_bstrFuncName` pole.

FIF_RETURNTYPE inicializace/použít `m_bstrReturnType` pole.

FIF_ARGS inicializace/použít `m_bstrArgs` pole.

FIF_LANGUAGE inicializace/použít `m_bstrLanguage` pole.

FIF_MODULE inicializace/použít `m_bstrModule` pole.

FIF_STACKRANGE inicializace/použít `m_addrMin` a `m_addrMax` (rozsah zásobníku) pole.

FIF_FRAME inicializace/použít `m_pFrame` pole.

FIF_DEBUGINFO inicializace/použít `m_fHasDebugInfo` pole.

FIF_STALECODE inicializace/použít `m_fStaleCode` pole.

FIF_ANNOTATEDFRAME inicializace/použít `m_fAnnotatedFrame` pole.

FIF_DEBUG_MODULEP inicializace/použít `m_pModule` pole.

FIF_FUNCNAME_FORMAT naformátuje název funkce. Výsledek se vrátí v `m_bstrFunName` pole a žádná další pole jsou vyplněna.

Přidá FIF_FUNCNAME_RETURNTYPE návratový typ `m_bstrFuncName` pole.

Přidá FIF_FUNCNAME_ARGS argumenty, které mají `m_bstrFuncName` pole.

Přidá FIF_FUNCNAME_LANGUAGE jazyk tak, aby `m_bstrFuncName` pole.

FIF_FUNCNAME_MODULE přidá název modulu, který se má `m_bstrFuncName` pole.

FIF_FUNCNAME_LINES přidá počet řádků `m_bstrFuncName` pole.

Přidá FIF_FUNCNAME_OFFSET `m_bstrFuncName` pole Posun v bajtech od začátku řádku, pokud `FIF_FUNCNAME_LINES` je zadán. Pokud `FIF_FUNCNAME_LINES` není zadán, nebo pokud čísla řádků nejsou k dispozici, přidá posun v bajtech od začátku funkci.

FIF_FUNCNAME_ARGS_TYPES přidá typ každého argumentu funkce `m_bstrFuncName` pole.

FIF_FUNCNAME_ARGS_NAMES přidá název každý argument funkce `m_bstrFuncName` pole.

FIF_FUNCNAME_ARGS_VALUES přidá hodnotu každý argument funkce `m_bstrFuncName` pole.

FIF_FUNCNAME_ARGS_ALL přidá typ, název a hodnotu všech argumentů `m_bstrFuncName` pole.

FIF_ARGS_TYPES typy argumentů jsou načtena a ve formátu.

FIF_ARGS_NAMES názvy argumentů se načte a ve formátu.

FIF_ARGS_VALUES hodnoty argumentů se načte a ve formátu.

Načíst FIF_ARGS_ALL a formát typ, název a hodnotu všech argumentů.

FIF_ARGS_NOFORMAT Určuje, že jsou argumenty nesmí být ve formátu (například není přidat otevírací a zavírací závorky seznamu argumentů ani přidat oddělovač mezi argumenty).

Při načítání hodnoty argumentů nesmí používat FIF_ARGS_NO_FUNC_EVAL Určuje, že funkce vyhodnocení (Vlastnosti).

FIF_FILTER_NON_USER_CODE ladicí stroj je k filtrování rámce neuživatelský kód tak, že nejsou zahrnuty.

FIF_ARGS_NO_TOSTRING neumožňují `ToString()` funkce zkušební nebo formátování při vrácení argumenty funkce.

Informace o snímcích FIF_DESIGN_TIME_EXPR_EVAL byste získali z hostovaná doména aplikace, nikoli hostitelský proces.

## <a name="remarks"></a>Poznámky
Tyto příznaky jsou předány [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) a [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) metody k označení pole, která mají být inicializovány v [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) strukturou nebo strukturami.

Tyto příznaky jsou také použity k označení polí s [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury jsou používány a platný, pokud vrátí strukturu. Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)
- [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)
