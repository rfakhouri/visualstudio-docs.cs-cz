---
title: Ladění v době návrhu - sady Visual Studio | Microsoft Docs
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
ms.openlocfilehash: c569ba018cfaa65cf2fec3edcf0676ef374db225
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="debug-at-design-time-in-visual-studio"></a>Ladění v době návrhu v sadě Visual Studio

V některých případech můžete chtít ladění kódu v návrhu čas místo, když aplikace běží. Můžete provést pomocí **Immediate** okno. Pokud chcete ladit kód XAML, který komunikuje s jiný kód, jako je například kód vazby dat, můžete použít **ladění** > **připojit k procesu** to provést.
  
### <a name="debug-at-design-time-using-the-immediate-window"></a>Ladění v době návrhu pomocí příkazové podokno  

Visual Studio můžete použít **Immediate** okno spuštění funkce nebo podprogramu, zatímco aplikace není spuštěna. Pokud funkce nebo podprogramu obsahuje zarážku, Visual Studio dojde k přerušení spuštění v odpovídajícím bodě. Ladicí program windows pak můžete zkontrolovat stav aplikací. Tato funkce je volána ladění v době návrhu.  

Následující příklad je v jazyce Visual Basic, ale **Immediate** okno je podporováno také v aplikacích pro c a C++.
  
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
  
2.  Nastavte zarážky v řádku, který čte, `s="Add BreakPoint Here"`.  
  
3.  Otevřete **Immediate** okno (**ladění** > **Windows** > **Immediate**) a zadejte následující příkaz v okno: `?MyFunction<enter>`  
  
4.  Ověřte, že byl vybrán zarážce a zda zásobníku volání přesná.  
  
5.  Na **ladění** nabídky, klikněte na tlačítko **pokračovat**a ověřte, že jste stále v režimu návrhu.  
  
6.  Zadejte následující příkaz v **Immediate** okno: `?MyFunction<enter>`  
  
7.  Zadejte následující příkaz v **Immediate** okno: `?MySub<enter>`  
  
8.  Ověřte, zda průchodu zarážkou a zkontrolujte hodnotu statické proměnné `i` v **místní hodnoty –** okno. Měl by mít hodnotu 3.  
  
9. Ověřte, zda je přesné zásobníku volání.  
  
10. Na **ladění** nabídky, klikněte na tlačítko **pokračovat**a ověřte, že jste stále v režimu návrhu.  

## <a name="debug-at-design-time-from-the-xaml-designer"></a>Ladění v době návrhu z Návrháře XAML

Může být užitečné k ladění kódu na pozadí z Návrháře XAML v některých scénářích vazby deklarativní data.

1. V projektu, přidejte novou stránku XAML, například *temp.xaml*. Nová stránka XAML ponechte prázdné. 

1. Zkompilujte řešení.

1. Otevřete *temp.xaml*, což způsobí načtení návrháře (*UwpSurface.exe* v aplikaci pro UPW, nebo *XDesProc.exe*), můžete připojit k němu v dalších krocích. 

1. Otevření nové instance sady Visual Studio. V nové instanci, otevřete **připojit k procesu** dialogové okno (**ladění** > **připojit k procesu**), můžete nastavit **přiřadit** pole, jako typ správný kód **spravovaného kódu (CoreCLR)** nebo typ správný kód v závislosti na vaší verzi rozhraní .NET. Vyberte správný návrháře proces ze seznamu a vyberte **Attach**.

    Pro UPW projektech zacílených na sestavení 16299 nebo novější, je proces návrháře *UwpSurface.exe*. WPF nebo verzích UWP předchozí 16299 návrháře proces se *XDesProc.exe*.

1. Během připojena k procesu, přepněte do projektu, otevřete místo ladění kódu a nastavit zarážky.

1. Nakonec otevřete stránku, která obsahuje kód XAML, který obsahuje datové vazby.

    Například můžete nastavit zarážky v kódu převaděče typu pro jazyk XAML následující, která sváže TextBlock v době návrhu.

    ```xaml
    <TextBlock Text="{Binding title, ConverterParameter=lower, Converter={StaticResource StringFormatConverter}, Mode=TwoWay}"  />
    ```
   Při načtení stránky je průchodu zarážkou.
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)
