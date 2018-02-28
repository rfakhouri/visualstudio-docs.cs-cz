---
title: IDebugProcessQueryProperties | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugProcessQueryProperties
ms.assetid: ce29a248-81a0-42c0-99a7-1606e8c548ec
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 66c2c3800d5f571595d7aec1a1e145cbccd38ff5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocessqueryproperties"></a>IDebugProcessQueryProperties
Toto rozhraní je implementováno modulem rozhraní rozšíření [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) implementátory informačních technologií. To umožňuje implementátor informace o ladění procesu prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProcessQueryProperties: IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Implementace tohoto rozhraní se získat informace o prostředí pro spuštění ladění procesu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugProcessQueryProperties`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[QueryProperty](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperty.md)|Dotazy na hodnotu vlastnosti.|  
|[QueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperties.md)|Dotazy na hodnoty vlastností.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je implementováno málokdy.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)