---
title: IDebugPort2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPort2
helpviewer_keywords:
- IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 91ee83167c681b713ea7d7a51a38d45b05fba4d2
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="idebugport2"></a>IDebugPort2
Toto rozhraní představuje port ladění na počítači.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vlastní port dodavatele implementuje toto rozhraní představují port ladění na počítači.  
  
 Pokud port podporuje odesílání událostí portu, musíte také implementovat <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní pro podporu <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní, které pak poskytuje [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) nebo [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) vrátit toto rozhraní představující požadovaném portu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugPort2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|Vrátí název portu.|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|Vrátí identifikátor port.|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|Vrátí požadavek použít k vytvoření port (Pokud je k dispozici).|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|Vrátí dodavatele portu pro tento port.|  
|[Getprocess –](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|Vrátí rozhraní pro proces zadaný identifikátor procesu.|  
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|Vytvoří výčet všech procesů spuštěných na port.|  
  
## <a name="remarks"></a>Poznámky  
 Místní port poskytuje přístup ke všem procesy a programy spuštěné v místním počítači. Další porty může představovat sériový kabel připojení k zařízení se systémem Windows CE nebo síťové připojení k počítači bez modelu DCOM. `IDebugPort2` Rozhraní se používá k najít název a identifikátor portu, výčet všech procesů spuštěných na port a zadejte svá zařízení pro spuštění a ukončení procesů na portu.  
  
## <a name="requirements"></a>Požadavky  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)