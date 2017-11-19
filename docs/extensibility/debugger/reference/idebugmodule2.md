---
title: IDebugModule2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugModule2
helpviewer_keywords: IDebugModule2 interface
ms.assetid: 24c2a126-f4ab-4891-8509-8ef99b994c08
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dd8600c592993d24d07add88425e534d5ae99867
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmodule2"></a>IDebugModule2
Toto rozhraní představuje modul – to znamená, spustitelný soubor jednotky program – například knihovny DLL.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugModule2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představují modul a poskytnout přístup k informacím o tomto modulu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [getmodule –](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md) vrátí toto rozhraní. Zasílá DE [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md) rozhraní pro správce relaci ladění (SDM) pomocí [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) metoda.  
  
 Toto rozhraní se může také vracet v [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury (který se vrátí po volání [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)).  
  
 [Další](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md) také vrátí hodnotu toto rozhraní ([enummodules –](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) vrátí [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md) rozhraní).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugModule2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)|Získá [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) tento modul, který popisuje.|  
|[ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md)|ZASTARALÉ. NEPOUŽÍVEJTE. Znovu načte symboly pro tento modul.|  
  
## <a name="remarks"></a>Poznámky  
 Informace o modulu lze zobrazit v **moduly** okno IDE.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [Getmodule –](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)   
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)