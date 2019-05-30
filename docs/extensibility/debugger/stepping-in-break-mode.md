---
title: Krokování v režimu pozastavení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e3a8688f32a97d27ee6f6e2d18fcea8e25feaac2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348546"
---
# <a name="stepping-in-break-mode"></a>Krokování v režimu pozastavení
Následující část popisuje proces, který nastane, pokud je v režimu přerušení ladicího programu a musí krokovat kód:

## <a name="stepping-process"></a>Krokování procesu

1. Volání [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) s [STEPKIND](../../extensibility/debugger/reference/stepkind.md) a [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) argumenty k provedení kroku.

2. Po dokončení kroku odeslat [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) jako událostí ukončení.

## <a name="see-also"></a>Viz také:
- [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)