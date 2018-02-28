---
title: IDebugStackFrame3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugStackFrame3
helpviewer_keywords:
- IDebugStackFrame3 interface
ms.assetid: 39af2f57-0a01-42b8-b093-b7fbc61e2909
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a45859fe78df3907df680b7716f743ff411ca3f3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstackframe3"></a>IDebugStackFrame3
Toto rozhraní rozšiřuje [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) zpracování zachycené výjimek.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugStackFrame3 : IDebugStackFrame2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje modul ladění (DE) pro stejný objekt, který implementuje [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní pro podporu zachycené výjimky.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugStackFrame2` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod zděděno z [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md), `IDebugStackFrame3` poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Interceptcurrentexception –](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)|Zpracovává výjimku pro aktuální rámec zásobníku před všechny regulární výjimek.|  
|[GetUnwindCodeContext](../../../extensibility/debugger/reference/idebugstackframe3-getunwindcodecontext.md)|Vrátí kontext kódu pokud dojde k unwind zásobníku.|  
  
## <a name="remarks"></a>Poznámky  
 Výjimku zachycené znamená, že ladicí program může zpracovat výjimku před všechny rutiny normální výjimek jsou volány čas spuštění. Brání výjimku v podstatě znamená, že čas spuštění předstírají, že se nachází i v případě, že neexistuje žádná obslužná rutina výjimky.  
  
 [Interceptcurrentexception –](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) je volána v průběhu všech událostí zpětného volání normální výjimky (jedinou výjimkou je, pokud ladění ve smíšeném režimu kódu (spravovaných a nespravovaných kódu), v takovém případě nemůže být zachyceny výjimku během zpětné volání poslední chance). Pokud je DE neimplementuje `IDebugStackFrame3`, nebo je DE vrátí chybu z IDebugStackFrame3::`InterceptCurrentException` (například `E_NOTIMPL`), pak ladicího programu bude obvykle ošetření výjimky.  
  
 Tím, že zachytává výjimku, ladicího programu povolit uživatelům změnit stav programu laděné a poté pokračovat v provádění v místě, kde byla výjimka vydána.  
  
> [!NOTE]
>  Zachycené výjimky jsou povoleny pouze ve spravovaném kódu, tedy v programu, který běží v rámci běžné Language Runtime (CLR).  
  
 Modul ladění označuje, že ji podporuje zachycení výjimky nastavením "metricExceptions" na hodnotu 1 v době běhu pomocí `SetMetric` funkce. Další informace najdete v tématu [SDK pomocníci pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)