---
title: IDebugEvent2 | Dokumentace Microsoftu
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
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7fc387733e1472afe5f21f5e0638374ebda9f677
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675113"
---
# <a name="idebugevent2"></a>IDebugEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugevent2).  
  
Toto rozhraní se používá ke komunikaci důležitých informací o ladění, jako je například pozastavení na zarážce a méně důležité informace, jako je například zprávu ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) a vlastní port dodavatele implementovat toto rozhraní na stejný objekt jako všechny ostatní události rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Pomocí rozhraní argument ID (IID) k [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) nebo [události](../../../extensibility/debugger/reference/idebugportevents2-event.md), Správce ladění relace (SDM) volá [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na `IDebugEvent2` rozhraní získat rozhraní odpovídající události.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetAttributes –](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|Získá atributy pro tuto událost ladění.|  
  
## <a name="remarks"></a>Poznámky  
 Konkrétnější události rozhraní, jako například [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), není odvozen z rozhraní IDebugEvent2, ale místo toho jsou implementované jako samostatné rozhraní na stejný objekt jako `IDebugEvent2`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Události](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)

