---
title: Změna hodnoty místní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, changing values programmatically
ms.assetid: 8407d3df-d38a-4328-82d1-98084bef43ec
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b24bf833336245ff36384e3f34d83b27ed44a62c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669939"
---
# <a name="changing-the-value-of-a-local"></a>Změna hodnoty místní hodnoty
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [změna hodnoty lokální](https://docs.microsoft.com/visualstudio/extensibility/debugger/changing-the-value-of-a-local).  
  
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Pokud je zadán novou hodnotu v poli hodnota **místní hodnoty** okně ladění balíčku předává řetězec, jak byla zadána vyhodnocovací filtr výrazů (EE). EE vyhodnotí tento řetězec, který může obsahovat jednoduchý hodnota nebo výraz a uloží výsledné hodnoty přidružené místní.  
  
 Toto je přehled procesu změna hodnoty místní:  
  
1.  Poté, co uživatel zadá novou hodnotu, Visual Studio volá [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) na [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objekt přidružený k místní.  
  
2.  `IDebugProperty2::SetValueAsString` provádí následující úlohy:  
  
    1.  Vyhodnotí jako řetězec, který má hodnotu.  
  
    2.  Vytvoří vazbu přidruženého [IDebugField](../../extensibility/debugger/reference/idebugfield.md) objektu získat [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) objektu.  
  
    3.  Převede hodnotu na řadu bajtů.  
  
    4.  Volání [SetValue](../../extensibility/debugger/reference/idebugobject-setvalue.md) převést hodnotu bajtů do paměti tak laděnému programu k nim přistupovat.  
  
3.  Visual Studio se aktualizuje **lokální** zobrazení (naleznete v tématu [zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md) podrobnosti).  
  
 Tento postup slouží také ke změně hodnoty proměnné v **Watch** okno kromě toho je `IDebugProperty2` objekt přidružený k hodnotu místní proměnné, která se použije namísto `IDebugProperty2` objekt přidružený k místní samotný.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Ukázková implementace změny hodnot](../../extensibility/debugger/sample-implementation-of-changing-values.md)  
 Používá ukázkový MyCEE pro jednotlivé kroky v procesu změny hodnot.  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů modulu CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md)

