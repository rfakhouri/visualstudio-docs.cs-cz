---
title: Přechod do režimu přerušení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- break mode
- debugging [Debugging SDK], entering break mode
ms.assetid: e9a8a241-cd21-4d4e-999a-283554c288b1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8da96c1df3423665ed223fecdd43007ba5a6e671
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60045665"
---
# <a name="enter-break-mode"></a>Přejít do režimu přerušení
Následující informace popisují proces, který nastane, pokud zarážky po krokování do funkce, běží na řádek zdrojového kódu, který v sobě obsahuje ukazatel nebo k zarážce.

## <a name="break-mode-process"></a>Proces v režimu přerušení

1. Ladicí stroj (DE) odešle [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md), nebo jiných událostí ukončení způsobit rozhraní IDE do režimu přerušení.

2. SDM získává informace v zásobníku volání z vlákna, následujícím způsobem:

    - [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)

    - [IEnumDebugFrameInfo2::GetCount](../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)

    - [IEnumDebugFrameInfo2::Next](../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)

    - [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) k získání informací o zdrojovém kódu

    - [IDebugDocumentContext2::GetName](../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md) získání názvu souboru

    - [IDebugDocumentContext2::GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) možné získat rozsah – příkaz

    - [IDebugStackFrame2::GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md) zobrazíte informace o paměti

## <a name="see-also"></a>Viz také:
- [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)