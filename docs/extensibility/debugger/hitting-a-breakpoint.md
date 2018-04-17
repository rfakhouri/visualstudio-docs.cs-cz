---
title: Stiskne zarážku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9f4788f8a038a274d6d94b4edf368e30ef495665
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="hitting-a-breakpoint"></a>Stiskne zarážky
Následující část popisuje proces při ladění modulu (DE) dotkne zarážku při spuštění nebo krokování:  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>Řešení potíží s přístupů zarážek  
  
1.  Odešle DE [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) rozhraní jako **EVENT_SYNC_STOP**.  
  
2.  Volá správce ladicí relace (SDM) [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) získat zarážek, který byl vybrán.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)