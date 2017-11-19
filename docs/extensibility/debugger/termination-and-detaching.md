---
title: "Ukončení a odpojení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- programs, termination events
- debug engines, detaching from programs
ms.assetid: 268c1e51-6363-45d1-964c-1ab99bdfa4f9
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9efd8e7bdaf9f75f3c3d81f7738d6bfb078cfcb2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="termination-and-detaching"></a>Ukončení a odpojení
Následující část popisuje běžné ukončení.  
  
## <a name="discussion"></a>Diskusní  
 Po [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) nebo [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) rozhraní bude pokračovat, pokud nejsou žádné zarážky, výjimky, chyby nebo nekonečné smyčky v aplikaci chcete ladit, k dokončení se bude program laděné spouštět. To je normální ukončení.  
  
 Je nutné odeslat [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) implementovat normální ukončení. To vyžaduje implementace [IDebugProgramDestroyEvent2::GetExitCode](../../extensibility/debugger/reference/idebugprogramdestroyevent2-getexitcode.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření vlastních ladění modulu](../../extensibility/debugger/creating-a-custom-debug-engine.md)