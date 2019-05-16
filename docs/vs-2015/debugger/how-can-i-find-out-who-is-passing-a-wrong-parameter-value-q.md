---
title: Jak zjistím, kdo předává nesprávnou hodnotu parametru? | Dokumenty Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.parameters
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], parameters
- parameters [debugger]
- passing parameters, troubleshooting wrong values
- functions [debugger], detecting wrong parameter values
- parameter values, troubleshooting
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b0787a0d700859e7728762fd7846911fcd41e369
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65704555"
---
# <a name="how-can-i-find-out-who-is-passing-a-wrong-parameter-value"></a>Jak zjistím, kdo předává nesprávnou hodnotu parametru?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Popis problému  
 Chybná hodnota parametru je předána jedné z mých funkcí. Tato funkce je volána odkudkoliv. Jak zjistím, co ho nesprávnou hodnotu předává?  
  
## <a name="solution"></a>Řešení  
  
#### <a name="to-resolve-this-problem"></a>Chcete-li vyřešit tento problém  
  
1. Nastavte zarážku umístění na začátek funkce.  
  
2. Klikněte pravým tlačítkem myši zarážka a vyberte **podmínku**.  
  
3. V **podmínka zarážky** dialogové okno, klikněte na **podmínku** zaškrtávací políčko. Zobrazit [Advanced zarážky](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).  
  
4. Zadejte výraz, jako například `Var==3`, do textového pole, ve kterém `Var` je název parametru, který obsahuje chybnou hodnotu, a `3` je předaná chybná hodnota k němu.  
  
5. Vyberte **true** přepínač a klikněte na tlačítko **OK** tlačítko.  
  
6. Nyní spusťte program znovu. Zarážka způsobí zastavení na začátku funkce programu při `Var` parametr má hodnotu `3`.  
  
7. Použití okna zásobník volání najděte volající funkci a přejděte k jejímu zdrojovému kódu. Další informace najdete v tématu [jak: Použijte okno zásobníku volání](../debugger/how-to-use-the-call-stack-window.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Zarážky](https://msdn.microsoft.com/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
