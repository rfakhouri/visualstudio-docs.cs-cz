---
title: "Klíč rozhraní vyhodnocování výrazu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, interfaces
ms.assetid: 1cac9aa3-0867-4e12-a16e-1e90abbc0fb6
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a03d419122f3cb72b3b9573279b41bc0de2636c5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="key-expression-evaluator-interfaces"></a>Výraz klíče vyhodnocování rozhraní
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Při vyhodnocování výrazu (EE), spolu s kontext vyhodnocení zápisu, měli byste se seznámit s následující rozhraní.  
  
## <a name="interface-descriptions"></a>Popis rozhraní  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
     Obsahuje jedinou metodu, [getaddress –](../../extensibility/debugger/reference/idebugaddress-getaddress.md), který získá datová struktura, představuje aktuálního bodu provádění. Tato struktura dat je jedním z tři argumenty, které modul ladění (DE) předá do [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) metody k vyhodnocení výrazu. Toto rozhraní je implementováno obvykle zprostředkovatelem symbol.  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
     Má [vazby](../../extensibility/debugger/reference/idebugbinder-bind.md) metodu, která získá oblasti paměti, která obsahuje aktuální hodnotu symbol. Zadané obou obsahující metodu, reprezentovanou [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) objekt a symbolu, reprezentována [IDebugField](../../extensibility/debugger/reference/idebugfield.md) objekt, `IDebugBinder::Bind` vrátí hodnotu symbolu. `IDebugBinder`Obvykle je implementováno modulem DE.  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
     Představuje jednoduchého datového typu. Pro více komplexní typy, jako je například pole a metody, použijte odvozené [IDebugArrayField](../../extensibility/debugger/reference/idebugarrayfield.md) a [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) rozhraní v uvedeném pořadí. [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) je jinou důležitá odvozené rozhraní, které představuje symboly obsahující další symboly, například metody nebo třídy. `IDebugField` Rozhraní (a odvozené) je obvykle implementované zprostředkovatelem symbol.  
  
     `IDebugField` Objekt lze použít k vyhledání název a typ symbolu a společně s [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) objektu, můžete použít k vyhledání jeho hodnotu.  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
     Představuje skutečný bity hodnota doby běhu symbolu. [Vytvoření vazby](../../extensibility/debugger/reference/idebugbinder-bind.md) trvá [IDebugField](../../extensibility/debugger/reference/idebugfield.md) objekt, který představuje symbol a vrátí [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) objektu. [GetValue](../../extensibility/debugger/reference/idebugobject-getvalue.md) metoda vrátí hodnotu symbolu ve vyrovnávací paměti. Zavedenými obvykle implementuje toto rozhraní představující hodnotu vlastnosti v paměti.  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
     Toto rozhraní představuje vyhodnocovací filtr výrazů sám sebe. Metoda klíče je [analyzovat](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md), která vrátí [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) rozhraní.  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
     Toto rozhraní představuje výraz analyzovaný připravené k vyhodnocení. Metoda klíče je [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) která vrátí IDebugProperty2 představující hodnotu a typ výrazu.  
  
-   [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)  
  
     Toto rozhraní představuje hodnotu a její typ a je výsledkem vyhodnocení výrazu.  
  
## <a name="see-also"></a>Viz také  
 [Kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md)