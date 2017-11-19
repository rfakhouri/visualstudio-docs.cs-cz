---
title: "Krokování s v režimu pozastavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 011de9ce3e4e1445354f907dcf56a0f4ecbef6bc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="stepping-in-break-mode"></a>Krokování s v režimu pozastavení
Následující text popisuje proces, který nastane, když je v režimu pozastavení ladicího programu a musí krok prostřednictvím kódu:  
  
## <a name="stepping-process"></a>Krokování s procesu  
  
1.  Volání [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) s [STEPKIND](../../extensibility/debugger/reference/stepkind.md) a [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) argumenty provést krok.  
  
2.  Po dokončení kroku odeslat [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) jako událost zastavit.  
  
## <a name="see-also"></a>Viz také  
 [Události volání ladicí program](../../extensibility/debugger/calling-debugger-events.md)