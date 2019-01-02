---
title: IDebugPortRequest2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortRequest2
helpviewer_keywords:
- IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1a05f84d685ac33203461dfc1b0f515cb45f67c3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53876926"
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
Toto rozhraní popisuje port. Tento popis se používá k přidání portu pro dodavatele portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio obvykle implementuje toto rozhraní právě získání portu ladění od jiného dodavatele portu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je předána do [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) vytvořit port pro ladění. Volání [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md) vrátí toto rozhraní představující žádost použitý k vytvoření portu na prvním místě.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugPortRequest2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|Získá název portu, který chcete vytvořit.|  
  
## <a name="remarks"></a>Poznámky  
 Ladicí stroj obvykle nekomunikuje s dodavatele portu a nebude mít žádný použijte pro toto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)