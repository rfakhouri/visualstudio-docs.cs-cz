---
title: "Jak zjistím, kdo předává nesprávnou hodnotu parametru? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.parameters
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], parameters
- parameters [debugger]
- passing parameters, troubleshooting wrong values
- functions [debugger], detecting wrong parameter values
- parameter values, troubleshooting
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 77c4953840c879a14406003f0bafffe98908cd95
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-can-i-find-out-who-is-passing-a-wrong-parameter-value"></a>Jak zjistím, kdo předává nesprávnou hodnotu parametru?
## <a name="problem-description"></a>Popis problému  
 Hodnota nesprávný parametr je předáván na jeden z mých funkce. Tato funkce je volána z po celém na místě. Jak můžete najít na co je předání chybnou hodnotu?  
  
## <a name="solution"></a>Řešení  
  
#### <a name="to-resolve-this-problem"></a>Chcete-li vyřešit tento problém  
  
1.  Nastavení zarážek umístění na začátku funkce.  
  
2.  Klikněte pravým tlačítkem na zarážce a vyberte **podmínku**.  
  
3.  V **zarážek podmínku** dialogové okno, kliknutím na tlačítko **podmínku** zaškrtávací políčko. V tématu [Advanced zarážky](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).  
  
4.  Zadání výrazu, jako například `Var==3`, do textového pole, kde `Var` je název parametru, který obsahuje chybnou hodnotu, a `3` je chybná hodnota předaná do ní.  
  
5.  Vyberte **má hodnotu True** přepínač a klikněte na **OK** tlačítko.  
  
6.  Nyní spusťte program znovu. Zarážce vede k zastavení na začátku funkce při `Var` parametru má hodnotu `3`.  
  
7.  Okno zásobník volání použijte k vyhledání volání funkce a přejděte do jeho zdrojový kód. Další informace najdete v tématu [postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md).  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Zarážky](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)