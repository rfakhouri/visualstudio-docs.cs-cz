---
title: IDebugModule2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugModule2
helpviewer_keywords:
- IDebugModule2 interface
ms.assetid: 24c2a126-f4ab-4891-8509-8ef99b994c08
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4ea20dac16cdffbac24cbca68c1a337a250ea8cc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922766"
---
# <a name="idebugmodule2"></a>IDebugModule2
Toto rozhraní představuje modul – to znamená, spustitelný soubor částí programu, například knihovny DLL.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugModule2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní k reprezentaci modulu a poskytují přístup k informacím o tomto modulu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [getmodule –](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md) vrátí toto rozhraní. DE odešle [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md) rozhraní při použití Správce ladění relace (SDM) [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) metoda.  
  
 Toto rozhraní může být také vrácen v [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) strukturu (který je vrácen voláním [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)).  
  
 [Další](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md) také vrátí hodnotu toto rozhraní ([enummodules –](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) vrátí [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md) rozhraní).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugModule2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)|Získá [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) tento modul, který popisuje.|  
|[ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md)|ZASTARALÉ. NEPOUŽÍVEJTE. Znovu načte symboly pro tento modul.|  
  
## <a name="remarks"></a>Poznámky  
 Informace o modulu lze zobrazit **moduly** okno integrovaného vývojového prostředí.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [Getmodule –](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)   
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)