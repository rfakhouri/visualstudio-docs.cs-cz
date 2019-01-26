---
title: IDebugBreakEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBreakEvent2
helpviewer_keywords:
- IDebugBreakEvent2 interface
ms.assetid: 57dfdbc2-4e68-4dbf-9579-006cd6fb1c62
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 218c1d01a693b81472a40430fa60455073bb8fb4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54929007"
---
# <a name="idebugbreakevent2"></a>IDebugBreakEvent2
Toto rozhraní informuje správce ladění relace (SDM), že asynchronní přerušení byla úspěšně dokončena.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugBreakEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní pro podporu uživatelů konce v programu. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) musí implementovat rozhraní na stejný objekt jako toto rozhraní (SDM používá [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání SDM [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) když uživatel požaduje program laděn, která se má pozastavit. Když se program úspěšně byla pozastavena, DE odešle `IDebugBreakEvent2` událostí. Tato událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) poskytnutých SDM při připojení k laděnému programu funkce zpětného volání.  
  
## <a name="remarks"></a>Poznámky  
 Například může uživatel vybrat **přerušit vše** příkaz **ladění** nabídky, aby program, který běží v nekonečné smyčce. SDM říká programu, aby zastavit voláním [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md). Odešle DE `IDebugBreakEvent2` při nakonec zastavení programu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)