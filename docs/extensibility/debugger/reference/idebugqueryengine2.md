---
title: IDebugQueryEngine2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugQueryEngine2
helpviewer_keywords: IDebugQueryEngine2 interface
ms.assetid: 8f0e1838-a818-4459-9138-a3dceb7408de
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b5545d49776e31b60719a49e4dbdca14d7dfdda3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugqueryengine2"></a>IDebugQueryEngine2
Toto rozhraní umožňuje relace ladění manager (SDM) načíst rozhraní, které představuje modul ladění (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugQueryEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje DE u objektů, které implementují rozhraní nejběžnější DE (například [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md), [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md), a [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)) v Chcete-li povolit přístup k [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) rozhraní DE sám sebe.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](/cpp/atl/queryinterface) na typické rozhraní DE k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugQueryEngine2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetEngineInterface](../../../extensibility/debugger/reference/idebugqueryengine2-getengineinterface.md)|Získá rozhraní, které je vlastní ladění modulu (DE).|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je implementováno obvykle v objektu, který implementuje [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní za účelem podpory seřazené příčiny procházení funkce; to znamená, když je ladicí program krokování s mimo funkci, Další funkce provést nemusí být předchozí funkce v zásobníku, ale funkce v jiné vlákno úplně. Definice "příčiny", najdete v článku [Glosář ladicí program Visual Studio](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)