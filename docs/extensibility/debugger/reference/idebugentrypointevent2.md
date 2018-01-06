---
title: IDebugEntryPointEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEntryPointEvent2
helpviewer_keywords: IDebugEntryPointEvent2 interface
ms.assetid: a15d1cc3-97b7-438c-8d24-c23149708f42
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ed45b6d0166a92e9547b7ad76e189108cd2b5e02
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugentrypointevent2"></a>IDebugEntryPointEvent2
Modul ladění (DE) pošle toto rozhraní pro relaci ladění správce (SDM), když program se chystá provést jeho první instrukci uživatelského kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEntryPointEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE toto rozhraní implementuje jako součást normální operace. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) k přístupu `IDebugEvent2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událostí, je-li program laděné byla načtena a je připravený k provedení první pokyn uživatelského kódu. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při jej připojit k programu laděné.  
  
## <a name="remarks"></a>Poznámky  
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) je odeslána, když program se chystá provést úplně první instrukcí. Například `IDebugEntryPoint2` je odeslána, když program je připraven ke spuštění uživatele `main` funkce.  
  
 Když je DE odešle `IDebugEntryPointEvent2`, aktuální pozici kód by měl být u první instrukce uživatelského kódu, třeba `main`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)