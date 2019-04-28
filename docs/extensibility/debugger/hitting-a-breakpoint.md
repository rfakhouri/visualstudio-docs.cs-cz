---
title: Dosažení zarážky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1286af8222703028d5a8a1bd2dbb0d990ca7e30c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62889902"
---
# <a name="hit-a-breakpoint"></a>Na zarážku
Následující část popisuje proces, při ladicího stroje (DE) narazí na zarážku při spuštění nebo při krokování:

## <a name="troubleshoot-a-hit-breakpoint"></a>Řešení potíží s průchodů zarážky

1. Odešle DE [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) rozhraní jako **EVENT_SYNC_STOP**.

2. Správce ladění relace (SDM) volá [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) zobrazíte, které bylo dosaženo zarážky.

## <a name="see-also"></a>Viz také:
- [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)