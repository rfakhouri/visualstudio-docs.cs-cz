---
title: Ladění LINQ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, LINQ
- LINQ, viewing results in debugger
- LINQ, debugging
- LINQ, stepping
- LINQ, edit and continue
ms.assetid: dbae26cb-ac5f-4312-b474-b9f29714f4c6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 52b4c9eb74207e966c17a212b9a9181293581297
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-linq"></a>Ladění LINQ
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podporuje ladění jazyka integrované dotazu (LINQ) kód, s omezeními. Funkce nejvíce ladění pracovat s příkazy LINQ, včetně krokování, nastavení zarážek a zobrazení výsledků v ladicím programu windows. Toto téma popisuje hlavní omezení ladění LINQ.  
  
##  <a name="BKMK_ViewingLINQResults"></a> Zobrazení výsledků LINQ  
 Výsledek příkazu LINQ můžete zobrazit pomocí datatips – okno kukátka a dialogové okno QuickWatch. Použijete-li okno zdroj, je možné pozastavit ukazatele na dotazu v okně zdroje a zobrazí datového tipu. Můžete zkopírovat proměnnou LINQ a vložte jej do kukátko – okno nebo QuickWatch – dialogové okno.  
  
 V technologii LINQ nebude hodnocen dotazu, pokud je vytvořen nebo deklarovat, ale jenom v případě, že se používá dotaz. Dotaz proto nemá hodnotu, dokud je vyhodnocena. Úplný popis vytvoření dotazu a zkušební, najdete v části [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries) nebo [zápis vaše první dotaz LINQ](/dotnet/visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query).  
  
 Pokud chcete zobrazit výsledek dotazu, se musí vyhodnotit ladicího programu ho. Tato implicitní hodnocení, které dojde při zobrazení výsledku dotazu LINQ ladicí program, má některé účinky, které byste měli zvážit:  
  
-   Každého vyhodnocení dotazu trvá určitou dobu. Rozšíření uzlu výsledky trvá určitou dobu. Pro některé dotazy může způsobit snížení výkonu znatelné opakované vyhodnocení.  
  
-   Vyhodnocení dotazu může mít za následek vedlejší účinky, které se změní na hodnotu data a stav vašeho programu. Ne všechny dotazy mají vedlejší účinky. Pokud chcete zjistit, zda dotaz může bezpečně vyhodnotit bez vedlejší účinky, musíte pochopit kód, který implementuje dotazu.  
  
##  <a name="BKMK_SteppingAndLinq"></a> Krokování a LINQ  
 Při ladění kódu LINQ krokování má několik rozdílů chování, které byste měli vědět o.  
  
### <a name="linq-to-sql"></a>Technologie LINQ to SQL  
 V technologii LINQ to SQL dotazy kód predikátem je nad rámec řízení ladicího programu. Proto nelze krok do predikátu kódu. Jakýkoli dotaz kompilovaný na strom výrazu vytvoří kód, který je mimo kontrolu ladicího programu.  
  
### <a name="stepping-in-visual-basic"></a>Krokování s v jazyce Visual Basic  
 Pokud jsou krokování programu Visual Basic a ladicí program zaznamená deklaraci dotazu, není krok do deklaraci, ale označuje celý deklaraci jako jediný příkaz. K tomuto chování dochází, protože dotaz není vyhodnocen, dokud se označuje jako. Další informace najdete v tématu [Úvod do LINQ v jazyku Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq).  
  
 Pokud projděte následující příklad kódu, jsou vysvětlené deklarace dotazu nebo vytvoření dotazu jako jediný příkaz ladicího programu.  
  
```  
Function MyFunction(ByVal x As Char)  
    Return True  
End Function  
  
Sub Main()  
    'Query creation  
    Dim x = From it In "faoaoeua" _  
            Where MyFunction(it) _  
            Select New With {.a = it}  
  
    ' Query execution  
    For Each cur In x  
        Console.WriteLine(cur.ToString())  
    Next  
End Sub  
```  
  
 Když krok znovu ladicího programu označuje `For Each cur In x`. V dalším kroku kroky do funkce `MyFunction`. Po procházení `MyFunction`, ho přejde zpět na `Console.WriteLine(cur.ToSting())`. Na žádný bod ho krok prostřednictvím predikátem kódu v deklaraci dotazu, i když ladicího programu vyhodnotit tento kód.  
  
### <a name="replacing-a-predicate-with-a-function-to-enable-stepping-visual-basic"></a>Nahraďte predikát funkce umožňující taktování (Visual Basic)  
 Pokud máte na krok prostřednictvím predikátem kódu pro účely ladění, můžete nahradit predikát volání funkce, která obsahuje původní kód predikátem. Předpokládejme například, že máte tento kód:  
  
```  
Dim items() as integer ={1, 2, 3, 4, 5, 6, 7, 8, 9, 10}  
  
' Get the even numbers  
Dim query = From nextInt in items Where nextInt Mod 2 = 0 Select nextInt  
  
For each item in query  
      Console.WriteLine(item)  
Next  
```  
  
 Nové funkce, volá se můžete přesunout kód predikátem `IsEven`:  
  
```  
Dim items () as integer ={1, 2, 3, 4, 5, 6, 7, 8, 9, 10}  
  
' Get the even numbers  
Dim query = From nextInt in items Where IsEven(nextInt) Select nextInt  
  
For each item in query  
      Console.WriteLine(item)  
Next  
...   
Function IsEven(item As =Integer) as Boolean  
      Return item Mod 2 = 0  
End Function  
```  
  
 Revidované dotaz volá funkci `IsEven` při každém průchodu přes `items`. Ladicí program windows můžete použít zda každá položka splňuje zadanou podmínku, a můžete krokovat kód v `IsEven`. Predikát v tomto příkladu je docela jednoduché. Ale pokud budete mít predikát obtížnější, které máte k ladění, tato technika může být velmi užitečné.  
  
##  <a name="BKMK_EditandContinueNotSupportedforLINQ"></a> Upravit a pokračovat není podporována pro LINQ  
 Upravit a pokračovat, podporuje změny dotazů LINQ s omezeními. Podrobnosti najdete v tématu [Šif podporované změny](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits))
  
## <a name="see-also"></a>Viz také  
 [Ladění SQL](http://msdn.microsoft.com/en-us/f27c17e6-1d90-49f2-9fc0-d02e6a27f109)    
 [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)   
 [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)   
 [Úvod do LINQ v jazyku Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)