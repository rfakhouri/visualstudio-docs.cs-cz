---
title: "Návod: Ladění v době návrhu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5869279a7bafb11368b7fb232e6ca68ca7d98478
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-debugging-at-design-time"></a>Návod: Ladění v době návrhu
Visual Studio můžete použít **Immediate** okno spuštění funkce nebo podprogramu, zatímco aplikace není spuštěna. Pokud funkce nebo podprogramu obsahuje zarážku, Visual Studio dojde k přerušení spuštění v odpovídajícím bodě. Ladicí program windows pak můžete zkontrolovat stav aplikací. Tato funkce je volána ladění v době návrhu.  
  
 Následující postup ukazuje, jak můžete tuto funkci používat.  
  
### <a name="to-hit-breakpoints-from-the-immediate-window"></a>K volání zarážek z příkazové podokno  
  
1.  Vložte následující kód do konzolové aplikace jazyka Visual Basic:  
  
    ```  
    Module Module1  
  
        Sub Main()  
            MySub()  
        End Sub  
  
        Function MyFunction() As Decimal  
            Static i As Integer  
            i = i + 1  
            Dim s As String  
  
            s = "Add Breakpoint here"  
            Return 4  
        End Function  
  
        Sub MySub()  
            MyFunction()  
        End Sub  
    End Module  
    ```  
  
2.  Nastavte zarážky v řádku, který čte, `s="Add BreakPoint Here"`.  
  
3.  Zadejte následující příkaz v **Immediate** okno:`?MyFunction<enter>`  
  
4.  Ověřte, že byl vybrán zarážce a zda zásobníku volání přesná.  
  
5.  Na **ladění** nabídky, klikněte na tlačítko **pokračovat**a ověřte, že jste stále v režimu návrhu.  
  
6.  Zadejte následující příkaz v **Immediate** okno:`?MyFunction<enter>`  
  
7.  Zadejte následující příkaz v **Immediate** okno:`?MySub<enter>`  
  
8.  Ověřte, zda průchodu zarážkou a zkontrolujte hodnotu statické proměnné `i` v **místní hodnoty –** okno. Měl by mít hodnotu 3.  
  
9. Ověřte, zda je přesné zásobníku volání.  
  
10. Na **ladění** nabídky, klikněte na tlačítko **pokračovat**a ověřte, že jste stále v režimu návrhu.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)