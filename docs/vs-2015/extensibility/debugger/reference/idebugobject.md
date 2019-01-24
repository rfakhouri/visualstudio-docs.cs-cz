---
title: IDebugObject | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugObject
helpviewer_keywords:
- IDebugObject interface
ms.assetid: 05cd8bf4-c9ee-4b49-b782-2263c33067d6
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 157e4ef5a6f8875a85de1108f94028ef25d25075
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767219"
---
# <a name="idebugobject"></a>IDebugObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní představuje objekt, který má vazač vytvoří k zapouzdření hodnoty symbolů a výrazy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugObject : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocovače výrazů implementuje toto rozhraní k reprezentaci objektu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je základní třída pro všechny objekty, které používá vyhodnocovací filtr výrazů v analyzované výrazy. Je vrácený voláním [svázat](../../../extensibility/debugger/reference/idebugbinder-bind.md) metoda. [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) získá rozhraní více specializované z tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugObject`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md)|Získá velikost objektu.|  
|[GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)|Získá hodnotu objektu ve formě po sobě jdoucích řady bajtů.|  
|[SetValue](../../../extensibility/debugger/reference/idebugobject-setvalue.md)|Nastaví hodnotu objektu z po sobě jdoucích řady bajtů.|  
|[SetReferenceValue](../../../extensibility/debugger/reference/idebugobject-setreferencevalue.md)|Nastaví odkaz na hodnotu tohoto objektu.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugobject-getmemorycontext.md)|Získá kontext paměti, který představuje adresu hodnotu objektu.|  
|[GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md)|Vytvoří kopii spravovaný objekt v adresním prostoru ladicího stroje.|  
|[IsNullReference](../../../extensibility/debugger/reference/idebugobject-isnullreference.md)|Ověřuje, zda tento objekt je odkaz s hodnotou null.|  
|[IsEqual](../../../extensibility/debugger/reference/idebugobject-isequal.md)|Porovná objekt do tohoto objektu.|  
|[IsReadOnly](../../../extensibility/debugger/reference/idebugobject-isreadonly.md)|Určuje, zda tento objekt je jen pro čtení.|  
|[IsProxy](../../../extensibility/debugger/reference/idebugobject-isproxy.md)|Určuje, zda je objekt transparentní proxy server.|  
  
## <a name="remarks"></a>Poznámky  
 Chyba při vyhodnocování výrazu používá k reprezentaci objektů v strom analýzy toto rozhraní jako základní třídy.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)   
 [Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)
