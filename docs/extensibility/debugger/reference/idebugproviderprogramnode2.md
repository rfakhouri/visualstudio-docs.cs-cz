---
title: IDebugProviderProgramNode2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProviderProgramNode2
helpviewer_keywords:
- IDebugProviderProgramNode2
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c80f86ac24d6e9e214b19a3e8c4564bdf11523b9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53846175"
---
# <a name="idebugproviderprogramnode2"></a>IDebugProviderProgramNode2
Toto rozhraní zařazuje rozhraní týkající se programu přes hranice procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProviderProgramNode2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní na stejný objekt, který implementuje [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) pro podporu zařazování rozhraní přes hranice procesu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugProgramNode2` rozhraní k získání tohoto rozhraní. Pokud toto rozhraní nelze získat, nepodporuje DE zařazování rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|Získá zadaný rozhraní přes hranice procesu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je implementováno po DE spuštění v prostoru procesu odděleně od laděného programu: třeba když DE běží v prostoru procesu Visual Studio namísto procesního prostoru programu, který se právě ladí.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)