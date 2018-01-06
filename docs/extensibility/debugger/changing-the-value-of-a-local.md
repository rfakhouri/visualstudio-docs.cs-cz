---
title: "Změna hodnoty místní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, changing values programmatically
ms.assetid: 8407d3df-d38a-4328-82d1-98084bef43ec
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 03e6acb4ee9756d0bbb14a6e3667375d32cafba9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="changing-the-value-of-a-local"></a>Změna hodnoty místní
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Pokud je zadán novou hodnotu v poli hodnota **místní hodnoty –** okně balíček ladění předá řetězec, jak byla zadána, vyhodnocovací filtr výrazů (EE). EE vyhodnotí tento řetězec, který může obsahovat jednoduché hodnotu nebo výraz a ukládá výslednou hodnotu v přidružené místní.  
  
 Toto je přehled procesu změna hodnoty místní:  
  
1.  Poté, co uživatel zadá nová hodnota, Visual Studio volá [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) na [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objekt přidružený k místní.  
  
2.  `IDebugProperty2::SetValueAsString`provádí následující úlohy:  
  
    1.  Vyhodnotí řetězec k vytvoření hodnoty.  
  
    2.  Váže přidruženého [IDebugField](../../extensibility/debugger/reference/idebugfield.md) objekt, který chcete získat [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) objektu.  
  
    3.  Převede hodnotu na řadu bajtů.  
  
    4.  Volání [SetValue](../../extensibility/debugger/reference/idebugobject-setvalue.md) uvést bajtů hodnotu do paměti, takže k nim měli přístup programu laděné.  
  
3.  Visual Studio aktualizuje **místní hodnoty –** zobrazení (najdete v části [zobrazení místní hodnoty –](../../extensibility/debugger/displaying-locals.md) podrobnosti).  
  
 Tento postup se používá také ke změně hodnoty proměnné v **sledovat** okno s výjimkou se nachází `IDebugProperty2` objekt přidružený k hodnotě místní, který se používá namísto `IDebugProperty2` objekt přidružený k místní sám sebe.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Ukázková implementace změny hodnot](../../extensibility/debugger/sample-implementation-of-changing-values.md)  
 Pomocí ukázkové MyCEE krok procesem změna hodnot.  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md)