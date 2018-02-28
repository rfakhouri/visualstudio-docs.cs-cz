---
title: IDebugAlias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugAlias
helpviewer_keywords:
- IDebugAlias interface
ms.assetid: 3cc4c9a4-7805-4239-b00e-eb4a024f3c55
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f984f9454aa646663d2888c4241c2ed385188cd7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugalias"></a>IDebugAlias
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Představuje alias číselné proměnné. Alias je jednoduše jiný název proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugAlias : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocení výrazu (EE) implementuje toto rozhraní pro podporu číselné aliasy pro proměnné.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) vytvoří alias pro určitý objekt. Chcete-li vyhledat aliasy, použijte [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md) nebo [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Tyto metody jsou definovány v `IDebugAlias` rozhraní.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Funkce GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md)|Získá objekt, na který odkazuje tento alias.|  
|[GetName –](../../../extensibility/debugger/reference/idebugalias-getname.md)|Získá název aliasu.|  
|[GetICorDebugValue](../../../extensibility/debugger/reference/idebugalias-geticordebugvalue.md)|Načte `ICorDebugValue` rozhraní, která poskytuje přístup k spravovaný kód informace o tomto objektu (pouze pro spravovaný kód).|  
|[Uvolnění.](../../../extensibility/debugger/reference/idebugalias-dispose.md)|Označuje to, jako alias už používá.|  
  
## <a name="remarks"></a>Poznámky  
 Alias je desetinné číslo ve formátu řetězce následovanou znakem #, například 1001#.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)   
 [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md)   
 [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)