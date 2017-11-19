---
title: IDebugArrayObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayObject
helpviewer_keywords: IDebugArrayObject method
ms.assetid: a1c8e77e-dee1-4748-a516-6ab032a8f54f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2a93ae51788b2a0d93bcd677e0802dd2cf5a82ed
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugarrayobject"></a>IDebugArrayObject
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní představuje objekt array.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugArrayObject : IDebugObject  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocení výrazu implementuje toto rozhraní představují pole.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní můžete získat pomocí tohoto rozhraní [QueryInterface](/cpp/atl/queryinterface) Pokud objekt představuje pole.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na `IDebugObject` rozhraní, tyto metody jsou implementované v `IDebugArrayObject` rozhraní.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetCount –](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md)|Získá počet elementů v poli.|  
|[Getelement –](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)|Získá element pole.|  
|[GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)|Získá všechny elementy pole.|  
|[Getrank –](../../../extensibility/debugger/reference/idebugarrayobject-getrank.md)|Získá pořadí pole.|  
|[Getdimensions –](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md)|Získá rozměry pole.|  
  
## <a name="remarks"></a>Poznámky  
 Vyhodnocení výrazu toto rozhraní používá k reprezentaci pole v strom analýzy.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)