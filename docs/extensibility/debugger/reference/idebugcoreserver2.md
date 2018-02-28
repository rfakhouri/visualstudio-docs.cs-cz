---
title: IDebugCoreServer2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCoreServer2
helpviewer_keywords:
- IDebugCoreServer2 interface
ms.assetid: 9c47d0a6-9eb1-464e-bd44-fa2b552d4d36
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 31961d62c2ef7a253a16a5384dfa6b5e69209a97
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver2"></a>IDebugCoreServer2
Toto rozhraní umožňuje představují a získat informace ze serveru na počítači v síti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCoreServer2 : IUknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio implementuje toto rozhraní představují serveru. Každá instance sady Visual Studio vytvoří instanci tohoto rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Vlastní port dodavatele obdrží toto rozhraní je volání [událostí](../../../extensibility/debugger/reference/idebugportevents2-event.md).  
  
 Modul ladění můžete získat toto rozhraní nepřímo prostřednictvím volání [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) (která vrací [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md), rozhraní, které je odvozený od `IDebugCoreServer2`).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugCoreServer2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)|Získá název a atributy počítače.|  
|[GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)|Získá název počítače.|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)|Získá dodavatele port, který již existuje na počítači.|  
|[GetPort](../../../extensibility/debugger/reference/idebugcoreserver2-getport.md)|Získá port, který již existuje na počítači.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)|Enumerátor pro všechny porty se vytvoří na počítači.|  
|[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)|Enumerátor pro všechny dodavatelů port vytvoří na počítači.|  
|[GetMachineUtilities_V7](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineutilities-v7.md)|Získá nástroje počítač pro počítač.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je také použít Visual Studio a vyhledejte procesy spuštěné na počítačích v síti.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [Události](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)   
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)