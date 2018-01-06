---
title: IDebugStackFrame2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStackFrame2
helpviewer_keywords: IDebugStackFrame2 interface
ms.assetid: bd212a6a-dcc6-4756-a77a-e8dfda38b104
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 457cfc4997ca02ca76b296e3b56fded244629e52
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstackframe2"></a>IDebugStackFrame2
Toto rozhraní představuje jeden zásobníku v zásobníku volání v konkrétní podprocesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugStackFrame2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představují rámce zásobníku.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) načíst [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) rozhraní. Volání [Další](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md) načíst [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktura, která obsahuje `IDebugStackFrame2` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugStackFrame2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|Získá kontext kód pro tento rámce zásobníku.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|Získá kontext dokumentu pro tento rámce zásobníku.|  
|[GetName –](../../../extensibility/debugger/reference/idebugstackframe2-getname.md)|Získá název rámce zásobníku.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)|Získá popis rámce zásobníku.|  
|[GetPhysicalStackRange](../../../extensibility/debugger/reference/idebugstackframe2-getphysicalstackrange.md)|Získá znázornění závislé na počítač rozsahu fyzické adresy přidružené k rámce zásobníku.|  
|[GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)|Získá kontext vyhodnocení pro provádění vyhodnocení výrazu v aktuálním kontextu rámce zásobníku a přístup z více vláken.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugstackframe2-getlanguageinfo.md)|Získá jazyk přidružené rámce zásobníku.|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)|Získá popis vlastnosti přidružené k rámce zásobníku.|  
|[Enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)|Vytvoří enumerátor pro zásobník vlastnosti rámce.|  
|[Getthread –](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)|Získá vlákno přidružené rámce zásobníku.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je získat jenom v případě, že program laděné se zastavilo na zarážce (buď způsobené zarážku sady uživatelů nebo výjimku). Z tohoto rozhraní získat kontextu výraz k vyhodnocení výrazů, mohou být vráceny seznam registrů nebo zásobníku volání můžete získat a zkontrolován.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)