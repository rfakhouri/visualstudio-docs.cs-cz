---
title: IDebugStackFrame2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame2
helpviewer_keywords:
- IDebugStackFrame2 interface
ms.assetid: bd212a6a-dcc6-4756-a77a-e8dfda38b104
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d534c5616bd32011fb4e84367911b9a8c1b29ab
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986940"
---
# <a name="idebugstackframe2"></a>IDebugStackFrame2
Toto rozhraní představuje jeden zásobníku v zásobníku volání v konkrétní vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugStackFrame2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní představující rámec zásobníku.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) k načtení [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) rozhraní. Volání [Další](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md) k načtení [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) strukturu, která obsahuje `IDebugStackFrame2` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugStackFrame2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|Získá kontext kódu pro tento rámec zásobníku.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|Získá kontext dokumentu pro tento rámec zásobníku.|  
|[GetName](../../../extensibility/debugger/reference/idebugstackframe2-getname.md)|Získá název rámce zásobníku.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)|Získá popis rámce zásobníku.|  
|[GetPhysicalStackRange](../../../extensibility/debugger/reference/idebugstackframe2-getphysicalstackrange.md)|Získá vyjádření závislé na počítači rozsahu fyzické adresy přidružený blok zásobníku.|  
|[GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)|Získá objekt context hodnocení pro provádění vyhodnocení výrazu v rámci kontextu aktuální rámec zásobníku a vlákna.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugstackframe2-getlanguageinfo.md)|Získá jazyk přidružený blok zásobníku.|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)|Získá popis vlastnosti přidružené k rámec zásobníku.|  
|[EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)|Vytvoří čítač pro zásobník snímků vlastnosti.|  
|[GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)|Získá přidružený blok zásobníku vlákna.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je získat pouze v případě, že laděný program se zastavil na zarážce (buď způsobené zarážky nastavené uživatelem nebo výjimku). Z tohoto rozhraní můžete získat objekt context výraz k vyhodnocení výrazů, může být vrácen seznam registrů nebo zásobníku volání můžete získat a prozkoumat.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)