---
title: Ukončení a odpojení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debug engines, detaching from programs
ms.assetid: 268c1e51-6363-45d1-964c-1ab99bdfa4f9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: efaeb409d49c31e47f66bb5d593d1da6a3d97919
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971556"
---
# <a name="termination-and-detaching"></a>Ukončení a odpojení
Následující část popisuje normální ukončení.  
  
## <a name="discussion"></a>Diskuse  
 Po [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) nebo [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) rozhraní bude pokračovat, pokud neexistují žádné zarážky, výjimky, chyby za běhu nebo nekonečné smyčky v aplikaci k ladění, laděný program se spustí do konce. Tento proces je normální ukončení.  
  
 Je nutné odeslat [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) implementovat normální ukončení. Normální ukončení vyžaduje spuštění [IDebugProgramDestroyEvent2::GetExitCode](../../extensibility/debugger/reference/idebugprogramdestroyevent2-getexitcode.md) metody.  
  
## <a name="see-also"></a>Viz také:  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)