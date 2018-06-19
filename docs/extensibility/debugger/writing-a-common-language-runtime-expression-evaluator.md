---
title: Zápis běžné vyhodnocení výrazu Runtime jazyka | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluators, tutorial
- expression evaluation, samples
- debugging [Debugging SDK], expression evaluators tutorial
ms.assetid: bd79d57f-8e0a-4e14-a417-0b1de28fa1b2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3ff2189bd80d2c5bbbc5253763e2ba07ef917d19
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135841"
---
# <a name="writing-a-common-language-runtime-expression-evaluator"></a>Zápis běžné vyhodnocení výrazu Runtime jazyka
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Vyhodnocení výrazu (EE) je součástí modulu ladění (DE), která zpracovává syntaxe a sémantiku programovací jazyk, který vytváří kód laděné. Výrazy musí být vyhodnocena v kontextu programovací jazyk. Například v některých jazycích znamená výraz "A + B" "Součet A a B." V jiných jazycích může znamenat stejný výraz "A nebo B." Proto samostatné EE musí být napsané pro každý programovací jazyk, který generuje kód objektu chcete ladit v integrovaném vývojovém prostředí sady Visual Studio.  
  
 Kód v kontextu programovací jazyk musí interpretovat některé aspekty ladění balíčku sady Visual Studio. Například při provádění zastaví na zarážce, všechny výrazy, které uživatel zadal do **sledovat** okna musí být vyhodnocena a zobrazí. Také uživatel může změnit hodnotu místní proměnné zadáním výrazu do **sledovat** okno nebo do **Immediate** okno.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Modul CLR a vyhodnocování výrazů](../../extensibility/debugger/common-language-runtime-and-expression-evaluation.md)  
 Vysvětluje, že pokud proprietární programovací jazyk jsou integraci do prostředí Visual Studio IDE, zápis EE schopná vyhodnocení výrazů v kontextu proprietární jazyka umožňuje zkompilovat do převodního jazyka Microsoft (MSIL) bez nutnosti psaní modul ladění.  
  
 [Architektura vyhodnocovače výrazů](../../extensibility/debugger/expression-evaluator-architecture.md)  
 Popisuje, jak požadovaným rozhraním EE implementace a volání common language runtime symbol zprostředkovatele (SP) a rozhraní vazače.  
  
 [Registrace vyhodnocovače výrazů](../../extensibility/debugger/registering-an-expression-evaluator.md)  
 Zaznamenává, že EE musí se registrovat jako objekt pro vytváření tříd se modul common language runtime a běhová prostředí sady Visual Studio.  
  
 [Implementace vyhodnocovače výrazů](../../extensibility/debugger/implementing-an-expression-evaluator.md)  
 Popisuje, jak proces vyhodnocení výrazu zahrnuje modul ladění (DE), zprostředkovatele symbol (SP), objekt vazače a vyhodnocovací filtr výrazů (EE).  
  
 [Zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md)  
 Popisuje, jak, při spuštění, pozastavení, balíček ladění volá DE zobrazíte seznam místní proměnné a argumenty.  
  
 [Vyhodnocení výrazu okna kukátka](../../extensibility/debugger/evaluating-a-watch-window-expression.md)  
 Dokumenty, jakým způsobem volá balíček Visual Studio ladění DE k určení aktuální hodnota každý výraz ve svém seznamu sledovat.  
  
 [Změna hodnoty místní hodnoty](../../extensibility/debugger/changing-the-value-of-a-local.md)  
 Vysvětluje, že při změně hodnotu místní, každý řádek místní hodnoty – okno je související objekt, který poskytuje název, typ a aktuální hodnota místní.  
  
 [Implementace vizualizérů typů a vlastních prohlížečů](../../extensibility/debugger/implementing-type-visualizers-and-custom-viewers.md)  
 Vysvětluje, které rozhraní musí být implementované která komponenta pro podporu typu vizualizérech a vlastní prohlížeče.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřitelnost programu Visual Studio Debugger](../../extensibility/debugger/visual-studio-debugger-extensibility.md)