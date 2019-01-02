---
title: IDebugArrayField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugArrayField
helpviewer_keywords:
- IDebugArrayField interface
ms.assetid: 9667b0a5-4295-46cc-9388-b75c1350be15
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a16be2cd972688ef27816caacba2b5b0cfb53d4b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53885650"
---
# <a name="idebugarrayfield"></a>IDebugArrayField
Toto rozhraní popisuje symbolu pole nebo typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugArrayField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Poskytovatel symbolů implementuje na stejný objekt, který implementuje toto rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní. Toto rozhraní je specializací, který představuje pole objektů.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](/cpp/atl/queryinterface) získat z tohoto rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, pokud [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) vrátí příznak `FIELD_TYPE_ARRAY`.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) a [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, toto rozhraní implementuje následující:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetNumberOfElements](../../../extensibility/debugger/reference/idebugarrayfield-getnumberofelements.md)|Získá počet prvků v poli.|  
|[GetElementType](../../../extensibility/debugger/reference/idebugarrayfield-getelementtype.md)|Získá typ prvku v poli.|  
|[GetRank](../../../extensibility/debugger/reference/idebugarrayfield-getrank.md)|Získá řád objektu array.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)