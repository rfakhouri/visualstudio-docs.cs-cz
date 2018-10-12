---
title: Krokování v režimu pozastavení | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6ac13b201534289cdb161980716bbfdeda7b969e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49240601"
---
# <a name="stepping-in-break-mode"></a>Krokování v režimu přerušení
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Následující část popisuje proces, který nastane, pokud je v režimu přerušení ladicího programu a musí krokovat kód:  
  
## <a name="stepping-process"></a>Krokování procesu  
  
1.  Volání [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) s [STEPKIND](../../extensibility/debugger/reference/stepkind.md) a [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) argumenty k provedení kroku.  
  
2.  Po dokončení kroku odeslat [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) jako událostí ukončení.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)

