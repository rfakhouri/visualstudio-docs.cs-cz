---
title: Dosažení zarážky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6d95abd66f248ca994d7712f1bf51519022de9d7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344049"
---
# <a name="hit-a-breakpoint"></a>Na zarážku
Následující část popisuje proces, při ladicího stroje (DE) narazí na zarážku při spuštění nebo při krokování:

## <a name="troubleshoot-a-hit-breakpoint"></a>Řešení potíží s průchodů zarážky

1. Odešle DE [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) rozhraní jako **EVENT_SYNC_STOP**.

2. Správce ladění relace (SDM) volá [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) zobrazíte, které bylo dosaženo zarážky.

## <a name="see-also"></a>Viz také:
- [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)