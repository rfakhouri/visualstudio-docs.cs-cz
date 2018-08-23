---
title: IDebugBreakpointUnboundEvent2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugBreakpointUnboundEvent2
helpviewer_keywords:
- IDebugBreakpointUnboundEvent2
ms.assetid: 6b1e1863-0c64-4d85-8ab9-aface522fdea
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c5b33a0f1881cb52b3a7f647128c1bddc330cff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670240"
---
# <a name="idebugbreakpointunboundevent2"></a>IDebugBreakpointUnboundEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugBreakpointUnboundEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbreakpointunboundevent2).  
  
Toto rozhraní informuje správce ladění relace (SDM), že byla vázaná zarážka svázána načíst program.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugBreakpointUnboundEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní jako součást jeho podporu pro zarážky. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) musí implementovat rozhraní na stejný objekt jako toto rozhraní (SDM používá [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) přístup `IDebugEvent2` rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událost, když vázaná zarážka nevázaná. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) poskytnutých SDM při připojení k laděnému programu funkce zpětného volání.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugBreakpointUnboundEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)|Získá zarážce, kterou začal být nevázaného.|  
|[Getreason –](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)|Získá z důvodů, proč nevázaná zarážku.|  
  
## <a name="remarks"></a>Poznámky  
 Při uvolnění ladicí stroj knihovny DLL nebo třídy, musí být všechny zarážky, které byly vázané na kód v tomto modulu svázána laděnému programu. `IDebugBreakpointUnboundEvent2` Odeslány pro každý nevázaného zarážku.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)

