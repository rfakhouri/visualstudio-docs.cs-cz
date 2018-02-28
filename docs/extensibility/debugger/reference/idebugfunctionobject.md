---
title: IDebugFunctionObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugFunctionObject
helpviewer_keywords:
- IDebugFunctionObject interface
ms.assetid: 8d94e97c-a9d1-400c-8a98-a44b5385b33a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 97f1960ad62026647026d836217becdb5221fcba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobject"></a>IDebugFunctionObject
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní představuje funkci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugFunctionObject : IDebugObject  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocení výrazu implementuje toto rozhraní představují funkci.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je specializované [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní a získaná pomocí [QueryInterface](/cpp/atl/queryinterface) na `IDebugObject` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod zděděno z [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md), `IDebugFunctionObject` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)|Vytvoří objekt primitivní datové.|  
|[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)|Vytvoří objekt pomocí konstruktoru.|  
|[CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md)|Vytvoří objekt se žádný konstruktor.|  
|[CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)|Vytvoří objekt array.|  
|[CreateStringObject](../../../extensibility/debugger/reference/idebugfunctionobject-createstringobject.md)|Vytvoří objekt řetězce.|  
|[Vyhodnocení](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)|Volání funkce a vrátí výslednou hodnotu jako objekt.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní umožňuje vyhodnocovací filtr výrazů představující funkce v strom analýzy. `Create` Metody tohoto rozhraní se používají k vytvoření objekty, které představují vstupní parametry metody. Funkce mohou být provedeny poté voláním [Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) metoda, která vrátí objekt, který reprezentuje návratovou hodnotu funkce.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)