---
title: IEnumDebugModules2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEnumDebugModules2
helpviewer_keywords:
- IEnumDebugModules2
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c87b22de02324544bbf1ea0919254535f6cc2702
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugmodules2"></a>IEnumDebugModules2
Toto rozhraní zobrazí seznam modulů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugModules2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představují seznam moduly zavedené programu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Visual Studio volání [enummodules –](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IEnumDebugModules2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|Načte zadaný počet modulů v posloupnosti výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|Přeskočí zadaný počet modulů v posloupnosti výčtu.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|Získá počet modulů.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio použije toto rozhraní primárně k aktualizaci **moduly** okno.  
  
 Pro účely ladění v sadě Visual Studio, je program logické posloupnost kód pokyny, které můžete mezi modulu hranice, proto potřeba seznamu modulů pro jeden [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní. První modul v seznamu obvykle obsahuje počáteční vstupní bod pro přidružený program.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Enummodules –](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)