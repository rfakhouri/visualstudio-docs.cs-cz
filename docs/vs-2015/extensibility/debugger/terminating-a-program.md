---
title: Ukončení programu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f0b9ad248751af0885fa4edc0275be2ede5ddd9f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54765235"
---
# <a name="terminating-a-program"></a>Ukončení programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Následuje popis ukončení jedné programu s jedním vláknem.  
  
## <a name="termination-process"></a>Ukončení procesu  
  
1. Odešle DE [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) platnou adresou [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md).  
  
2. Odešle DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) platnou adresou [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md).  
  
   Rozhraní IDE přejde do režimu návrhu. Ladicí stroj nebo běhové prostředí volá [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) se program odebrat z portu.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)
