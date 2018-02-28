---
title: IDebugCustomAttribute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCustomAttribute
helpviewer_keywords:
- IDebugCustomAttribute interface
ms.assetid: c5ae41e9-00b9-4cca-871d-b8de9ef390d1
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 48aeab8a09d4916c31c5e2b781427988cf352b25
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcustomattribute"></a>IDebugCustomAttribute
Toto rozhraní představuje vlastní atribut a může poskytnout název, nadřazené a třídy typu atributu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCustomAttribute : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje poskytovatele symbolu za účelem podpory vlastní atributy přidružené symbol. Obvykle je implementované u svého vlastního objektu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [Další](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md) vrátí toto rozhraní. Volání [enumcustomattributes –](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md) metoda vrátí [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugCustomAttribute`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetParentField](../../../extensibility/debugger/reference/idebugcustomattribute-getparentfield.md)|Získá pole, do kterého se aktuální atribut připojen.|  
|[GetAttributeTypeField](../../../extensibility/debugger/reference/idebugcustomattribute-getattributetypefield.md)|Získá typ vlastního atributu třídy.|  
|[GetName –](../../../extensibility/debugger/reference/idebugcustomattribute-getname.md)|Získá název vlastního atributu.|  
|[GetAttributeBytes](../../../extensibility/debugger/reference/idebugcustomattribute-getattributebytes.md)|Získá informace o atributu jako objekt blob bajtů.|  
  
## <a name="remarks"></a>Poznámky  
 Vlastní atribut je struktura pro C#, která poskytuje vlastní metadata spojená s konkrétní třída nebo metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)