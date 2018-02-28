---
title: IDebugOutputStringEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugOutputStringEvent2
helpviewer_keywords:
- IDebugOutputStringEvent2 interface
ms.assetid: 86596fd1-cecc-4813-8add-dc3d70068f9b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f222df8aa2a6fc35db08ceae3e8f49dfe7537960
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugoutputstringevent2"></a>IDebugOutputStringEvent2
Toto rozhraní je poslal modul ladění (DE) zadaný pro relaci ladění správce (SDM) do výstupního řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugOutputStringEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní k odeslání řetězec tak, aby **výstup** okno IDE. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) k přístupu `IDebugEvent2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událostí k odeslání řetězec tak, aby **výstup** okno. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při připojení k programu laděné.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metodě `IDebugOutputStringEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetString –](../../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)|Získá zobrazitelné zprávu.|  
  
## <a name="remarks"></a>Poznámky  
 Například v nespravovaném kódu, může pocházet řetězec, který má být výstup při program laděné odešle řetězec Win32 `OutputDebugString` funkce. Tento řetězec je zachycen DE a posílá SDM jako `IDebugOutputStringEvent2` událostí.  
  
 Použití [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md) odeslat zprávu, která vyžaduje odpověď uživatele.  
  
 Použití [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) odeslat chybovou zprávu, která nevyžaduje odpověď.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)