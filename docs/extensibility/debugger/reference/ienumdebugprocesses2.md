---
title: IEnumDebugProcesses2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugProcesses2
helpviewer_keywords:
- IEnumDebugProcesses2
ms.assetid: 06a1368f-10f0-44eb-af61-e388c2327111
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e7654338bfa04b2c48a8286f9996f9002a95bbd
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55023678"
---
# <a name="ienumdebugprocesses2"></a>IEnumDebugProcesses2
Toto rozhraní vytváří výčet procesů spuštěných na port pro ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugProcesses : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Dodavatel port. Tento vlastní port implementuje toto rozhraní uvést seznam procesů spuštěných na portu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Visual Studio volání [enumprocesses –](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md) k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugProcesses2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)|Načte zadaný počet procesů v sekvenci výčtu.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugprocesses2-skip.md)|Vynechá zadaný počet procesů v sekvenci výčtu.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugprocesses2-reset.md)|Návrat na začátek sekvence výčtu.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugprocesses2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprocesses2-getcount.md)|Získá počet procesů v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio používá toto rozhraní k naplnění **procesy** okna.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)