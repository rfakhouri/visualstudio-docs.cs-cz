---
title: "Ukončení programu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4d1cb3176585dce135b19f125af55db799fed4b9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="terminating-a-program"></a>Ukončení programu
Následuje popis ukončení jeden program s jedno vlákno.  
  
## <a name="termination-process"></a>Ukončení procesu  
  
1.  Odešle DE [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) platný [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md).  
  
2.  Odešle DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) platný [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md).  
  
 Prostředí IDE přejde do režimu návrhu. Ladění modul nebo volání běhové prostředí [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) odebrání programu z portu.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)