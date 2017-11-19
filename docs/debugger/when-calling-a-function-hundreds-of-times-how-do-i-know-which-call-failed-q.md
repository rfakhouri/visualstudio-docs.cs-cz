---
title: "Jak při opakovaném volání funkce zjistím, jaké volání bylo neúspěšné? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.functions
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- conditional breakpoints
- errors [debugger], function calls
- breakpoints, troubleshooting
- errors [debugger], finding which function call failed
- failures
- location breakpoint call failures
- errors [Visual Studio], function calls
- hit counts
- function calls, failure
- functions [debugger]
- Skip Count
ms.assetid: 66cfac86-f5be-4d3a-9329-d44cd74bc586
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd02b4debeefbdbfff4e0889329eddab7fabe46a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="when-calling-a-function-hundreds-of-times-how-do-i-know-which-call-failed"></a>Jak při opakovaném volání funkce zjistím, jaké volání bylo neúspěšné?
## <a name="problem-description"></a>Popis problému  
 Moje program se na volání určité funkce, `CnvtV`. Program pravděpodobně volání této funkce několik set časy předtím, než se nezdaří. Pokud lze nastavit bod přerušení umístění na `CnvtV`, aplikace přestane při každém volání této funkce a která nechci. I neznáte, jaké podmínky způsobit volání selže, takže nelze nastavit podmíněné zarážky. Co mám udělat?  
  
## <a name="solution"></a>Řešení  
 Můžete nastavit zarážky funkce se **dosáhl počet** pole na hodnotu tak velká, že ji nebude nikdy zpracována. V takovém případě vzhledem k tomu, že budete mít dojem, funkce `CnvtV` nazývá několik set dobu, může nastavit **dosáhl počet** na 1000 nebo více. Potom spusťte program a počkejte selhání volání. Pokud se nezdaří, otevřete okno zarážky a podívejte se na seznam zarážky. Breakpoint – můžete nastavit v `CnvtV` se zobrazí, za nímž následuje počet přístupů a počet zbývajících opakování:  
  
```  
CnvtV(int) (no condition) when hit count is equal to 1000 (currently 101)  
```  
  
 Teď víte, že funkce se nezdařila při 101st volání. Pokud resetujete zarážek s počet přístupů 101 a spusťte program znovu, program se zastaví u volání `CnvtV` který způsobuje její neočekávané selhání.  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Nastavení zarážek](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)