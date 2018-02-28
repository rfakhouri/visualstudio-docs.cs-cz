---
title: IDebugPortRequest2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPortRequest2
helpviewer_keywords:
- IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5b47a9bde47049c957af9f60e1d09d03b55c2359
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
Toto rozhraní popisuje port. Tento popis se používá k přidání port na portu dodavatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio obvykle implementuje toto rozhraní právě získávání port ladění od jiného dodavatele portu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je předána do [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) vytvoření portu ladění. Volání [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md) vrátí toto rozhraní představující žádost použít k vytvoření port na prvním místě.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugPortRequest2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|Získá název tohoto portu, který chcete vytvořit.|  
  
## <a name="remarks"></a>Poznámky  
 Modul ladění obvykle nekomunikuje s jiného dodavatele portu a bude mít bez použití tohoto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)