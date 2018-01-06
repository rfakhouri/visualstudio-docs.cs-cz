---
title: IDebugCustomAttributeQuery2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCustomAttributeQuery2
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
- IDebugCustomAttributeQuery2 interface
ms.assetid: 7cfa23e4-a05a-47a3-af6c-bd40c655014b
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 31df907fe13cd171da8e443d3b8af876adaf3c3f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcustomattributequery2"></a>IDebugCustomAttributeQuery2
Určuje existenci vlastních atributů pro toto pole a pokud existuje, vrátí informace o atributu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCustomAttributeQuery2 : IDebugCustomAttributeQuery  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje poskytovatele symbol pro stejný objekt, který implementuje [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) za účelem podpory vlastní atributy.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](/cpp/atl/queryinterface) k získání tohoto rozhraní z [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody **IDebugCustomAttributeQuery** rozhraní.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md)|Určuje, zda existuje vlastní atribut podle názvu.|  
|[Getcustomattributebyname –](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md)|Získá informace o atributu pro daný vlastní atribut.|  
  
 Kromě **IDebugCustomAttributeQuery** metod `IDebugCustomAttributeQuery2` implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Enumcustomattributes –](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)|Získá enumerátor pro všechny vlastní atributy připojené k toto pole.|  
  
## <a name="remarks"></a>Poznámky  
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) metoda může vrátit enumerátor pro všechny vlastní atributy definované pro toto pole.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)