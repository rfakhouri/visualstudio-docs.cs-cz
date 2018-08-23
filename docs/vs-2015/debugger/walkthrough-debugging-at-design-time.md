---
title: 'Návod: Ladění v době návrhu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd63fca37bbb55f99ecb99a18596c128451bd807
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670966"
---
# <a name="walkthrough-debugging-at-design-time"></a>Návod: Ladění v době návrhu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [návod: ladění v době návrhu](https://docs.microsoft.com/visualstudio/debugger/walkthrough-debugging-at-design-time).  
  
Můžete použít Visual Studio **okamžité** okno ke spuštění funkce nebo podprogramu, zatímco aplikace není spuštěna. Pokud funkce nebo podprogram obsahuje zarážku, sada Visual Studio přeruší běh v odpovídajícím bodě. Potom můžete ladicí program windows prozkoumat stav vaší aplikace. Tato funkce je volána ladění v době návrhu.  
  
 Následující postup ukazuje, jak můžete tuto funkci.  
  
### <a name="to-hit-breakpoints-from-the-immediate-window"></a>K dosažení zarážky v okně Immediate  
  
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
  
2.  Nastavit zarážku na řádek s informacemi, `s="Add BreakPoint Here"`.  
  
3.  Zadejte následující příkaz v **okamžité** okno: `?MyFunction<enter>`  
  
4.  Ověřte, že byla zarážka dosažena a zásobník volání je přesné.  
  
5.  Na **ladění** nabídky, klikněte na tlačítko **pokračovat**a ověřte, že jste stále v režimu návrhu.  
  
6.  Zadejte následující příkaz v **okamžité** okno: `?MyFunction<enter>`  
  
7.  Zadejte následující příkaz v **okamžité** okno: `?MySub<enter>`  
  
8.  Ověřte, že zarážce a zkontrolujte hodnotu statická proměnná `i` v **lokální** okna. Měl by mít hodnotu 3.  
  
9. Ověřte, zda je přesné zásobníku volání.  
  
10. Na **ladění** nabídky, klikněte na tlačítko **pokračovat**a ověřte, že jste stále v režimu návrhu.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)



