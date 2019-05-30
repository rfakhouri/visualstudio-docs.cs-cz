---
title: DEBUG_REASON | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_REASON
helpviewer_keywords:
- DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0502ab10398d37bcafee5316ba7e7566dbab4e01
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346170"
---
# <a name="debugreason"></a>DEBUG_REASON
Určuje, proč byl spuštěn proces pro ladění.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_DEBUG_REASON {
    DEBUG_REASON_ERROR         = 0,
    DEBUG_REASON_USER_LAUNCHED = 1,
    DEBUG_REASON_USER_ATTACHED = 2,
    DEBUG_REASON_AUTO_ATTACHED = 3,
    DEBUG_REASON_CAUSALITY     = 4
};
typedef DWORD DEBUG_REASON;
```

```csharp
public enum enum_DEBUG_REASON {
    DEBUG_REASON_ERROR         = 0,
    DEBUG_REASON_USER_LAUNCHED = 1,
    DEBUG_REASON_USER_ATTACHED = 2,
    DEBUG_REASON_AUTO_ATTACHED = 3,
    DEBUG_REASON_CAUSALITY     = 4
};
```

## <a name="fields"></a>Pole
`DEBUG_REASON_ERROR`\
Došlo k chybě nespecifickou (používá se jako výchozí podmínku Pokud žádná z nich důvodů, proč přizpůsobit).

`DEBUG_REASON_USER_LAUNCHED`\
Proces byl spuštěn na žádost uživatele.

`DEBUG_REASON_USER_ATTACHED`\
Již spuštěnému procesu byl připojen k uživatelem.

`DEBUG_REASON_AUTO_ATTACHED`\
Proces byl automaticky připojen k při jejím spuštění.

`DEBUG_REASON_CAUSALITY`\
Proces byl spuštěn z důvodu *Just-In-Time* ladění události (JIT).

## <a name="remarks"></a>Poznámky
Vrátilo [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)
