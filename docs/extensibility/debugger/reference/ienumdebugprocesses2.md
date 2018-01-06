---
title: IEnumDebugProcesses2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugProcesses2
helpviewer_keywords: IEnumDebugProcesses2
ms.assetid: 06a1368f-10f0-44eb-af61-e388c2327111
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 559d95834ccb8c7d0081a95a8412dccf12b1d8fc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugprocesses2"></a>IEnumDebugProcesses2
Toto rozhraní zobrazí procesů spuštěných na portu ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugProcesses : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vlastní port dodavatele implementuje toto rozhraní, které poskytují seznam procesů spuštěných na portu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Visual Studio volání [enumprocesses –](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md) k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IEnumDebugProcesses2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)|Načte zadaný počet procesů v posloupnosti výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugprocesses2-skip.md)|Přeskočí zadaný počet procesů v posloupnosti výčtu.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugprocesses2-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugprocesses2-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugprocesses2-getcount.md)|Získá počet procesů v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio použije k naplnění toto rozhraní **procesy** okno.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Enumprocesses –](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)