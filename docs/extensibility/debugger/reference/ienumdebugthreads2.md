---
title: IEnumDebugThreads2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugThreads2
helpviewer_keywords: IEnumDebugThreads2
ms.assetid: 1854f078-3b49-42c2-b65b-33e3b506fd63
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b03d9adbec92986ea8a1cf0f589bd451107a611f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugthreads2"></a>IEnumDebugThreads2
Tato interfac zobrazí vláken spuštěné v aktuální relaci ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugThreads2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představují seznam vláken v programu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [enumthreads –](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md) k získání tohoto rozhraní představující seznam všechna vlákna ve všech aplikacích spuštěných v určitém procesu. Volání [enumthreads –](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) k získání tohoto rozhraní představující seznam podprocesů spuštěných v programu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IEnumDebugThreads2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md)|Načte zadaný počet vláken v pořadí výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugthreads2-skip.md)|Přeskočí zadaný počet vláken v posloupnosti výčtu.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugthreads2-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugthreads2-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako stávající.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugthreads2-getcount.md)|Získá počet vláken v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio obvykle obdrží toto rozhraní aktualizace **vláken** okno i, získat první vlákno seznamu, aby bylo možné volat [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md), [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md), a [Krok](../../../extensibility/debugger/reference/idebugprocess3-step.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Enumthreads –](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md)   
 [Enumthreads –](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)   
 [Krok](../../../extensibility/debugger/reference/idebugprocess3-step.md)   
 [Pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md)   
 [Spuštění](../../../extensibility/debugger/reference/idebugprocess3-execute.md)