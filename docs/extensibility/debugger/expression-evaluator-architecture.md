---
title: Architektura vyhodnocování výrazu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- architecture, expression evaluators
- expression evaluators, architecture
- debugging [Debugging SDK], expression evaluators
ms.assetid: aad7c4c6-1dc1-4d32-b975-f1fdf76bdeda
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7fdcdfef67531af40027a2dfe8c731fe9ba5128f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107160"
---
# <a name="expression-evaluator-architecture"></a>Architektura vyhodnocování výrazu
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Integrace vlastní jazyk do balíčku sady Visual Studio ladění znamená implementace rozhraní vyhodnocování (EE) vyžaduje výraz a volání běžné zprostředkovatele běhu symbol jazyka (SP) a rozhraní vazač. Kontext, ve kterém se vyhodnotí výrazy jsou SP a vazače objekty, společně s aktuální adresou provádění. Informace, které tato rozhraní vytvářet a využívat představuje klíčové koncepty v architektuře EE.  
  
## <a name="overview"></a>Přehled  
  
### <a name="parsing-the-expression"></a>Analýza výraz  
 Při ladění programu, se vyhodnotí výrazy několik důvodů, ale vždy když program laděné se zastavilo na zarážce (zarážku umístit uživatelem nebo jeden způsobené výjimku). V tuto chvíli, kdy sady Visual Studio získává rámce zásobníku, je reprezentovaná [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní z modulu ladění (DE). Visual Studio pak zavolá [GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) získat [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní. Toto rozhraní představuje kontext, ve kterém můžete vyhodnotit výrazy; [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) je vstupní bod pro proces hodnocení. Až se tento bod všechny rozhraní implementují DE.  
  
 Když `IDebugExpressionContext2::ParseText` je volána, DE vytvoří EE přidružené jazyk zdrojového souboru, kde došlo k zarážce (DE také vytvoří SH v tomto okamžiku). Je reprezentována EE [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md) rozhraní. DE pak zavolá [analyzovat](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) převést výraz (v textové podobě) výraz analyzovaný, připraveni k vyhodnocení. Analyzovaná výrazu je reprezentována [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) rozhraní. Všimněte si, že výraz je obvykle analyzovat a nejsou hodnoceny v tomto okamžiku.  
  
 DE vytvoří objekt, který implementuje [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, PUT `IDebugParsedExpression` objektu do `IDebugExpression2` objekt a vrátí `IDebugExpression2` objektu z `IDebugExpressionContext2::ParseText`.  
  
### <a name="evaluating-the-expression"></a>Vyhodnocení výrazu  
 Visual Studio zavolá buď [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) nebo [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) při vyhodnocování výrazu Analyzovaná. Obě tyto metody volání [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) (`IDebugExpression2::EvaluateSync` volá metodu okamžitě, při `IDebugExpression2::EvaluateAsync` volá metodu prostřednictvím vlákna na pozadí) vyhodnocování výrazu Analyzovaná a vrátíte se [ IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní, které představuje hodnotu a typ Analyzovaná výrazu. `IDebugParsedExpression::EvaluateSync` používá zadaný SH, adresa a vazač převést Analyzovaná výraz na skutečnou hodnotu, reprezentována `IDebugProperty2` rozhraní.  
  
### <a name="for-example"></a>Například  
 Po zarážku je dosáhl v spuštěným programem, uživatel vybere možnost zobrazit proměnnou v **QuickWatch** dialogové okno. Toto dialogové okno zobrazí název proměnné, jeho hodnotu a její typ. Uživatel může změnit obvykle hodnota.  
  
 Když **QuickWatch** se zobrazí dialogové okno, název proměnné se zkontrolován odeslán jako text, který se [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md). Vrátí [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) objekt v tomto případě představující Analyzovaná výrazu, proměnnou. [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) je pak volat za účelem vytvoření `IDebugProperty2` objekt, který reprezentuje hodnota proměnné a typ, jakož i její název. Je tato informace, které se zobrazí.  
  
 Pokud uživatel změní hodnota proměnné [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) je volán s novou hodnotu, který změní hodnotu proměnné v paměti, použije se po návratu program spuštěn.  
  
 V tématu [zobrazení místní hodnoty –](../../extensibility/debugger/displaying-locals.md) další podrobnosti o této proces zobrazení hodnoty proměnných. V tématu [změna hodnoty místní](../../extensibility/debugger/changing-the-value-of-a-local.md) další podrobnosti o tom, jak změnit hodnoty proměnné.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md)  
 Poskytuje argumenty, které se předá, když je DE volá EE.  
  
 [Rozhraní vyhodnocovače klíčových výrazů](../../extensibility/debugger/key-expression-evaluator-interfaces.md)  
 Popisuje klíčové rozhraní potřebné při zápisu EE, společně s kontext vyhodnocení.  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Zobrazení místní hodnoty](../../extensibility/debugger/displaying-locals.md)   
 [Změna hodnoty místní hodnoty](../../extensibility/debugger/changing-the-value-of-a-local.md)