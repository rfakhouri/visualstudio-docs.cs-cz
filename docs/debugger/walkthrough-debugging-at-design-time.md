---
title: Ladění v době návrhu – Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 02/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f1235e6360ccc5f6c0677f7ec9acb1dd85cad226
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39180175"
---
# <a name="debug-at-design-time-in-visual-studio"></a>Ladění v době návrhu v sadě Visual Studio

V některých případech můžete chtít ladit kód v návrhu čas místo, když je spuštěná aplikace. Můžete provést pomocí **okamžité** okna. Pokud chcete ladit kód XAML, který pracuje jiný kód, jako je například data vazební kód, můžete použít **ladění** > **připojit k procesu** to udělat.
  
### <a name="debug-at-design-time-using-the-immediate-window"></a>Ladění v době návrhu pomocí okna Příkazy  

Můžete použít Visual Studio **okamžité** okno ke spuštění funkce nebo podprogramu, zatímco aplikace není spuštěna. Pokud funkce nebo podprogram obsahuje zarážku, sada Visual Studio přeruší běh v odpovídajícím bodě. Potom můžete ladicí program windows prozkoumat stav vaší aplikace. Tato funkce je volána ladění v době návrhu.  

V následujícím příkladu je v jazyce Visual Basic, ale **okamžité** okna je podporováno také v aplikacích jazyka C# a C++.
  
1.  Vložte následující kód do konzolové aplikace jazyka Visual Basic:  
  
    ```vb  
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
  
3.  Otevřít **okamžité** okno (**ladění** > **Windows** > **okamžité**) a zadejte následující příkaz v okno: `?MyFunction<enter>`  
  
4.  Ověřte, že byla zarážka dosažena a zásobník volání je přesné.  
  
5.  Na **ladění** nabídky, klikněte na tlačítko **pokračovat**a ověřte, že jste stále v režimu návrhu.  
  
6.  Zadejte následující příkaz v **okamžité** okno: `?MyFunction<enter>`  
  
7.  Zadejte následující příkaz v **okamžité** okno: `?MySub<enter>`  
  
8.  Ověřte, že zarážce a zkontrolujte hodnotu statická proměnná `i` v **lokální** okna. Měl by mít hodnotu 3.  
  
9. Ověřte, zda je přesné zásobníku volání.  
  
10. Na **ladění** nabídky, klikněte na tlačítko **pokračovat**a ověřte, že jste stále v režimu návrhu.  

## <a name="debug-at-design-time-from-the-xaml-designer"></a>Ladění v době návrhu v Návrháři XAML

Může být užitečné při ladění kódu na pozadí z Návrháře XAML v některých scénářích vazby deklarativní data.

1. Ve vašem projektu, přidejte novou stránku XAML, jako například *temp.xaml*. Nová stránka XAML nechte prázdné. 

1. Kompilaci vašeho řešení.

1. Otevřít *temp.xaml*, což způsobí načtení návrháře (*UwpSurface.exe* v aplikaci UWP, nebo *XDesProc.exe*), můžete k němu připojit v dalších krocích. 

1. Otevřete novou instanci sady Visual Studio. V nové instanci, otevřete **připojit k procesu** dialogové okno (**ladění** > **připojit k procesu**), můžete nastavit **připojit k** pole pro typ správný kód, jako například **spravovaného kódu (CoreCLR)** nebo zadejte správný kód v závislosti na vaší verzi rozhraní .NET. Vyberte správný proces návrháře ze seznamu a zvolte **připojit**.

    Pro UPW projekty cílené na sestavení 16299 nebo novější, je proces návrháře *UwpSurface.exe*. Pro WPF nebo UWP verzím 16299 proces návrháře je *XDesProc.exe*.

1. Během připojena k procesu, přepněte do projektu, otevřete ve kterém chcete ladit kód a nastavte zarážku.

1. Nakonec otevřete stránku, která obsahuje kód XAML, který obsahuje datové vazby.

    Například můžete nastavit zarážku v kódu konvertor typu pro následující XAML, který váže objektech TextBlock v době návrhu.

    ```xaml
    <TextBlock Text="{Binding title, ConverterParameter=lower, Converter={StaticResource StringFormatConverter}, Mode=TwoWay}"  />
    ```
   Když se stránka načte, zarážka se projeví.
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Základy ladicího programu](../debugger/getting-started-with-the-debugger.md)
