---
title: Implementace vyhodnocovací filtr výrazů | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
ms.assetid: e9ada7be-845e-4baa-bf8f-e4890e7ba490
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ed1df74c187b3f0a93e1a1ec84e8803bc164d223
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103341"
---
# <a name="implementing-an-expression-evaluator"></a>Implementace vyhodnocení výrazu
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Vyhodnocení výrazu je komplexní vztahu mezi modul ladění (DE), poskytovatele symbol (SP), objekt vazače a vyhodnocovací filtr výrazů (EE) sám sebe. Tyto čtyři součásti jsou připojené pomocí rozhraní, které jsou implementované jedna součást a spotřebovávají jiné.  
  
 EE trvá výrazu z DE ve formě řetězce a analyzuje nebo vyhodnotí ji. EE implementuje následující rozhraní, které se spotřebovávají DE:  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
 EE zavolá metodu objektu vazač, poskytl DE, k získání hodnoty symbolů a objektů. EE využívá následující rozhraní, které jsou implementované DE:  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
-   [IDebugArrayObject](../../extensibility/debugger/reference/idebugarrayobject.md)  
  
-   [IDebugFunctionObject](../../extensibility/debugger/reference/idebugfunctionobject.md)  
  
-   [IDebugPointerObject](../../extensibility/debugger/reference/idebugpointerobject.md)  
  
-   [IDebugManagedObject](../../extensibility/debugger/reference/idebugmanagedobject.md)  
  
-   [IEnumDebugObjects](../../extensibility/debugger/reference/ienumdebugobjects.md)  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
 Implementuje EE [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md). `IDebugProperty2` poskytuje mechanismus pro popisující výsledkem vyhodnocení výrazu, jako je například místní proměnné, primitivní nebo objekt, pro Visual Studio, který pak zobrazí příslušné informace v **místní hodnoty –**,  **Kukátko**, nebo **Immediate** okno.  
  
 SP je uveden EE podle DE požádá informace. SP implementuje rozhraní, které popisují adresy a pole, jako je například následující rozhraní a jejich produkty:  
  
-   [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
 EE využívá všechny tyto rozhraní.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Strategie implementace vyhodnocovače výrazů](../../extensibility/debugger/expression-evaluator-implementation-strategy.md)  
 Definuje třech krocích proces pro implementaci strategie výraz vyhodnocování (EE).  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)