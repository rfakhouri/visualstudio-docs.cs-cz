---
title: Krokování v režimu pozastavení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 95b4cbe8faa42e5eca87dadcb06aa604856e1b91
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53988855"
---
# <a name="stepping-in-break-mode"></a>Krokování v režimu pozastavení
Následující část popisuje proces, který nastane, pokud je v režimu přerušení ladicího programu a musí krokovat kód:  
  
## <a name="stepping-process"></a>Krokování procesu  
  
1.  Volání [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) s [STEPKIND](../../extensibility/debugger/reference/stepkind.md) a [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) argumenty k provedení kroku.  
  
2.  Po dokončení kroku odeslat [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) jako událostí ukončení.  
  
## <a name="see-also"></a>Viz také:  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)