---
title: IEnumDebugThreads2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugThreads2
helpviewer_keywords:
- IEnumDebugThreads2
ms.assetid: 1854f078-3b49-42c2-b65b-33e3b506fd63
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 97bc8383f990f6c0c35a402f2ab36b2595d82a9e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68147689"
---
# <a name="ienumdebugthreads2"></a>IEnumDebugThreads2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato interfac zobrazí vlákna spuštěná během aktuální relace ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugThreads2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní představující seznam vláken v programu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [enumthreads –](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md) získat toto rozhraní představující seznam všechna vlákna ve všech aplikacích spuštěných v procesu. Volání [enumthreads –](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) získat toto rozhraní představující seznam vlákna spuštěná v programu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugThreads2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md)|Načte zadaný počet vláken v pořadí výčtu.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugthreads2-skip.md)|Vynechá zadaný počet vláken v sekvenci výčtu.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugthreads2-reset.md)|Návrat na začátek sekvence výčtu.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugthreads2-clone.md)|Vytvoří čítač, který obsahuje stejné stav výčtu, jako je aktuální.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugthreads2-getcount.md)|Získá počet vláken v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio obvykle obdrží toto rozhraní se aktualizovat **vlákna** okno stejně jako získat první vlákno seznamu, aby bylo možné volat [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md), [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md), a [Krok](../../../extensibility/debugger/reference/idebugprocess3-step.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Enumthreads –](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md)   
 [Enumthreads –](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)   
 [Krok](../../../extensibility/debugger/reference/idebugprocess3-step.md)   
 [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md)   
 [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md)
