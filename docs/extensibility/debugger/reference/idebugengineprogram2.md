---
title: IDebugEngineProgram2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineProgram2
helpviewer_keywords:
- IDebugEngineProgram2 interface
ms.assetid: 151003a9-2e4d-4acf-9f4d-365dfa6b9596
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 896370d83634580e46f666a8fb9f56f768bf06a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengineprogram2"></a>IDebugEngineProgram2
Toto rozhraní podporuje vícevláknové ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEngineProgram2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění implementuje toto rozhraní pro podporu souběžných ladění z více vláken. Toto rozhraní je implementováno na stejný objekt, který implementuje [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](/cpp/atl/queryinterface) k získání tohoto rozhraní z `IDebugProgram2` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugEngineProgram2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Stop](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)|Zastaví všechny podprocesy spuštěné v této aplikaci.|  
|[WatchForThreadStep](../../../extensibility/debugger/reference/idebugengineprogram2-watchforthreadstep.md)|Sleduje provádění (nebo zastavení sledování pro spouštění) pro dané vlákno.|  
|[WatchForExpressionEvaluationOnThread](../../../extensibility/debugger/reference/idebugengineprogram2-watchforexpressionevaluationonthread.md)|Umožňuje (nebo zakáže) vyhodnocení výrazu proběhnout v daném vláknu i v případě, že tento program je zastavena.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní v reakci na volá sady Visual Studio [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událostí a k nastavení stavu "Sledování pro přístup z více vláken krok" a "Sledování pro výraz vyhodnocení na vláken" programu. [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) nazývá vždy, když je program zastavení; tato metoda poskytuje program pokusu o ukončení všechna vlákna.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)