---
title: EXCEPTION_STATE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EXCEPTION_STATE
helpviewer_keywords:
- EXCEPTION_STATE enumeration
ms.assetid: 597f4f4c-9b70-485c-b5dc-3c2e3aecc664
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8f05596b12151b3a40b87c6fc2f15659a38e3431
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337690"
---
# <a name="exceptionstate"></a>EXCEPTION_STATE
Určuje stav výjimky.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_EXCEPTION_STATE {
    EXCEPTION_NONE                          = 0x0000,
    EXCEPTION_STOP_FIRST_CHANCE             = 0x0001,
    EXCEPTION_STOP_SECOND_CHANCE            = 0x0002,
    EXCEPTION_STOP_USER_FIRST_CHANCE        = 0x0010,
    EXCEPTION_STOP_USER_UNCAUGHT            = 0x0020,
    EXCEPTION_STOP_ALL                      = 0x00FF,
    EXCEPTION_CANNOT_BE_CONTINUED           = 0x0100,

    // These are for exception types only
    EXCEPTION_CODE_SUPPORTED                = 0x1000,
    EXCEPTION_CODE_DISPLAY_IN_HEX           = 0x2000,
    EXCEPTION_JUST_MY_CODE_SUPPORTED        = 0x4000,
    EXCEPTION_MANAGED_DEBUG_ASSISTANT       = 0x8000,

    // These are no longer used
    EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT      = 0x0004,
    EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT     = 0x0008,
    EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT = 0x0040,
    EXCEPTION_STOP_USER_UNCAUGHT_USE_PARENT     = 0x0080,
};
typedef DWORD EXCEPTION_STATE;
```

```csharp
public enum enum_EXCEPTION_STATE {
    EXCEPTION_NONE                          = 0x0000,
    EXCEPTION_STOP_FIRST_CHANCE             = 0x0001,
    EXCEPTION_STOP_SECOND_CHANCE            = 0x0002,
    EXCEPTION_STOP_USER_FIRST_CHANCE        = 0x0010,
    EXCEPTION_STOP_USER_UNCAUGHT            = 0x0020,
    EXCEPTION_STOP_ALL                      = 0x00FF,
    EXCEPTION_CANNOT_BE_CONTINUED           = 0x0100,

    // These are for exception types only
    EXCEPTION_CODE_SUPPORTED                = 0x1000,
    EXCEPTION_CODE_DISPLAY_IN_HEX           = 0x2000,
    EXCEPTION_JUST_MY_CODE_SUPPORTED        = 0x4000,
    EXCEPTION_MANAGED_DEBUG_ASSISTANT       = 0x8000,

    // These are no longer used
    EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT      = 0x0004,
    EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT     = 0x0008,
    EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT = 0x0040,
    EXCEPTION_STOP_USER_UNCAUGHT_USE_PARENT     = 0x0080,
};
```

## <a name="fields"></a>Pole
`EXCEPTION_NONE`\
Nedojde k zastavení při výjimce.

`EXCEPTION_STOP_FIRST_CHANCE`\
Zastavení při jeho prvním spuštění výjimky. Při popisu události výjimky, tento příznak signalizuje událost výjimky první odpovídající výjimce události.

`EXCEPTION_STOP_SECOND_CHANCE`\
Zastavení při jeho druhého spuštění výjimky. Při popisu události výjimky, označuje, že události výjimky je výjimka sekundu odpovídající události.

`EXCEPTION_STOP_USER_FIRST_CHANCE`\
Zastavení při jeho prvním spuštění výjimky režimu uživatele. Při popisu události výjimky, znamená, že události výjimky události výjimka první příležitosti uživatele.

`EXCEPTION_STOP_USER_UNCAUGHT`\
Zastavte, když není zachycena výjimka režimu uživatele. Při popisu události výjimky, označuje, že události výjimky je výjimka události režimu nezachycené uživatele.

`EXCEPTION_STOP_ALL`\
Zastavte na jakékoli výjimce. Nepoužívá se při popisu události výjimky.

`EXCEPTION_CANNOT_BE_CONTINUED`\
Při popisu události výjimky, označuje, že výjimka nemůže pokračovat z.

`EXCEPTION_CODE_SUPPORTED`\
Znamená, že výjimka má kód ho podporuje. Použité při zobrazování výjimku

`EXCEPTION_CODE_DISPLAY_IN_HEX`\
Označuje, že kód výjimky by měly zobrazovat v šestnáctkové soustavě. Použité při zobrazování výjimku.

`EXCEPTION_JUST_MY_CODE_SUPPORTED`\
Označuje, že kód výjimky podporuje JustMyCode. Použité při zobrazování výjimku.

`EXCEPTION_MANAGED_DEBUG_ASSISTANT`\
Označuje, že by měl ladicí program spravovaný kód zpracování výjimek. Pokud není set, výchozí ladicí program zpracovává výjimky. To je předáno [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md) metoda a nesmí se používat v [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) struktury.

`EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT`\
ZASTARALÉ, NEPOUŽÍVEJTE.

`EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT`\
ZASTARALÉ, NEPOUŽÍVEJTE.

`EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT`\
ZASTARALÉ, NEPOUŽÍVEJTE.

`EXCEPTION_STOP_USER_SECOND_CHANCE_USE_PARENT`\
ZASTARALÉ, NEPOUŽÍVEJTE.

## <a name="remarks"></a>Poznámky
Použít jako `dwState` člena [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) struktury k označení stavu výjimku a co se dá dělat o něm.

Tyto hodnoty jsou předány také [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md) metodu pro nastavení stavu všechny výjimky.

Tyto příznaky lze kombinovat s bitový operátor OR.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)
- [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)
