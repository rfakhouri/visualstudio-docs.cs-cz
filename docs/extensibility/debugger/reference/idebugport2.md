---
title: IDebugPort2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPort2
helpviewer_keywords:
- IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 06026276b6f9b37f005ee296d56ee17df5c75ca8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54962745"
---
# <a name="idebugport2"></a>IDebugPort2
Toto rozhraní představuje ladit na počítači.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Dodavatel port. Tento vlastní port implementuje toto rozhraní k reprezentaci ladit na počítači.  
  
 Pokud port, který podporuje odesílání událostí portů, musí také implementovat <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní pro podporu <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní, které poskytuje zase [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) nebo [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) vrátit toto rozhraní představující požadovaném portu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugPort2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|Vrátí název portu.|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|Vrátí identifikátor port.|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|Vrátí požadavku, použitý k vytvoření portu (Pokud je k dispozici).|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|Vrátí dodavatele portu pro tento port.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|Vrátí rozhraní pro proces zadaný identifikátor procesu.|  
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|Zobrazí všechny procesy spuštěné na portu.|  
  
## <a name="remarks"></a>Poznámky  
 Místní port poskytuje přístup ke všem procesy a programy spuštěné na místním počítači. Další portů může představovat sériový kabel připojení k zařízení se systémem Windows CE nebo síťové připojení k počítači bez modelu DCOM. `IDebugPort2` Rozhraní se používá k hledání názvu a identifikátoru portu a výčet všechny procesy spuštěné na portu. Zařízení pro spuštění a ukončení procesů na portu jsou implementovány v `IDebugPortEx2` rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)