---
title: Zobrazení místní hodnoty – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, displaying locals
ms.assetid: 62264cec-845b-4233-aed7-0b038fa79250
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 03a3f08498e8b046b02defd32083677b7f39e7e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="displaying-locals"></a>Zobrazení místní hodnoty
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Provádění vždycky probíhá v rámci této metody, také známé jako metodu obsahující nebo aktuální metoda. Při spuštění, pozastavení, Visual Studio volá modul ladění (DE) k získání seznamu místní proměnné a argumenty, se nazývají místní hodnoty – metody. Visual Studio zobrazí tyto lokální a jejich hodnoty v **místní hodnoty –** okno.  
  
 Místní hodnoty zobrazíte DE volá [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) metoda patřící do EE a provede jeho vyhodnocení kontext, který je, symbol zprostředkovatele (SP), aktuální adresa provádění a objekt vazače. Další informace najdete v tématu [kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md). Pokud volání úspěšné, `IDebugExpressionEvaluator::GetMethodProperty` metoda vrátí [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objekt, který představuje metodu, která obsahuje aktuální adresu provádění.  
  
 Volání DE [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) získat [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) objektu, který je použit filtr zobrazující vrátit pouze místní hodnoty – a vytvořit její výčet. Chcete-li vytvořit seznam [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md)struktury. Každá struktura obsahuje název, typ a hodnotu místní. Typ a hodnotu jsou uloženy jako formátované řetězce vhodný pro zobrazení. Název, typ a hodnota se obvykle zobrazují společně na jednom řádku z **místní hodnoty –** okno.  
  
> [!NOTE]
>  **QuickWatch** a **sledovat** proměnné s formátem stejný název, hodnotu a typ zobrazení systému windows. Ale tyto hodnoty jsou získány voláním [GetPropertyInfo –](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) místo `IDebugProperty2::EnumChildren`.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Ukázková implementace místních hodnot](../../extensibility/debugger/sample-implementation-of-locals.md)  
 Pomocí příklady krok procesem implementace místní hodnoty.  
  
## <a name="related-sections"></a>Související oddíly  
 [Kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md)  
 Vysvětluje, že když modul ladění (DE) vyvolá vyhodnocovací filtr výrazů (EE), předá tři argumenty.  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)