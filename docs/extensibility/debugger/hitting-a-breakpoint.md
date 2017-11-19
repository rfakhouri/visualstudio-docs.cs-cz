---
title: "Stiskne zarážku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73cdce5415dd50059dcd443f67424203430aba87
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="hitting-a-breakpoint"></a>Stiskne zarážky
Následující část popisuje proces při ladění modulu (DE) dotkne zarážku při spuštění nebo krokování:  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>Řešení potíží s přístupů zarážek  
  
1.  Odešle DE [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) rozhraní jako **EVENT_SYNC_STOP**.  
  
2.  Volá správce ladicí relace (SDM) [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) získat zarážek, který byl vybrán.  
  
## <a name="see-also"></a>Viz také  
 [Události volání ladicí program](../../extensibility/debugger/calling-debugger-events.md)