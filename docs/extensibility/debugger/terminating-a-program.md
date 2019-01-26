---
title: Ukončení programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 864141055487b598a8f91641f40fe4c027c53b6c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54918430"
---
# <a name="terminating-a-program"></a>Ukončení programu
Následující část popisuje ukončení jedné programu s jedním vláknem.  
  
## <a name="termination-process"></a>Ukončení procesu  
  
1. Odešle DE [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) platnou adresou [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md).  
  
2. Odešle DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) platnou adresou [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md).  
  
   Rozhraní IDE přejde do režimu návrhu. Ladicí stroj nebo běhové prostředí volá [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) se program odebrat z portu.  
  
## <a name="see-also"></a>Viz také:  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)