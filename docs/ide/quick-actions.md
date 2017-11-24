---
title: "Rychlé akce | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 4ae2344bb1bce77d7e71cadf34660db57380f6b4
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2017
---
# <a name="quick-actions"></a>Rychlé akce

[Rychlé akce](refactoring-code-generation-quick-actions.md#quick-actions) vám umožní snadno refactor, upravit kód, který představuje jednu akci a vygenerovat. Rychlé akce jsou k dispozici pro jazyk C#, [C++](/cpp/ide/writing-and-refactoring-code-cpp)a soubory s kódem jazyka Visual Basic. Některé akce jsou specifické pro jazyk a jiné jenom pro všechny jazyky. Můžete použít rychlé akce pomocí ikonou žárovky ![malé ikonou žárovky](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall"), nebo stisknutím kombinace kláves **Ctrl** + **.** Pokud je ukazatelem na příslušný řádek kódu.

Uvidíte, že žárovky je červenou vlnovkou a Visual Studio má návrhy pro informace o vyřešení problému. Například pokud máte chybu označená červenou vlnovkou, žárovky se zobrazí, když jsou k dispozici pro tuto chybu opravy. Pro žádný jazyk třetím stranám můžete zadat vlastní diagnostiky a návrhy, například jako součást sady SDK a Visual Studio žárovek bude light podle těchto pravidel.

## <a name="to-see-a-light-bulb"></a>Chcete-li zobrazit žárovky

1. V mnoha případech žárovek samovolně zobrazit při přesunutí ukazatele myši v místě chybu nebo na levém okraji editoru při přesunout znak v souladu, který v něm došlo k chybě. Až uvidíte červenou vlnovkou, můžete zobrazit žárovky myší. Může také způsobit žárovky zobrazíte při použití myši a klávesnice pro přejděte na libovolné místo v řádku vyskytl problém.

1. Stiskněte klávesu **Ctrl** + **.** kdekoli na řádek pro vyvolání žárovky a přejít přímo na seznam potenciálních opravy.

   ![Žárovky s ukazatele myši](../ide/media/vs2015_lightbulb_hover.png "VS2017_LightBulb_Hover")

## <a name="to-see-potential-fixes"></a>Chcete-li zobrazit potenciální opravy

Buď klikněte na šipku dolů, nebo zobrazit potenciální opravy odkaz zobrazíte seznam rychlé akce, které pro vás může trvat žárovky.

![Žárovky rozšířit](../ide/media/vs2015_lightbulb_hover_expanded.png "VS2017_LightBulb_hover_expanded")

## <a name="common-quick-actions"></a>Běžné rychlé akce

Zde jsou některé běžné rychlé akce, které platí pro obě C# a kód jazyka Visual Basic.

### <a name="add-missing-casesdefault-caseboth"></a>Přidejte chybějící případy nebo výchozího nebo obou případu

Při vytváření `switch` příkaz v C#, nebo `Select Case` příkaz v jazyce Visual Basic, můžete použít akce kód a automaticky tak přidejte chybějící případu položky, výchozí case – příkaz nebo obojí.  Pro prázdný příkaz takto:

```csharp
enum MyEnum
{
    Item1,
    Item2,
    Item3
}

...

MyEnum myEnum = MyEnum.Item1;

switch(myEnum)
{
}
```

```vb
Enum MyEnum
    Item1
    Item2
    Item3
End Enum

...

Dim myEnum as MyEnum = MyEnum.Item1

Select Case myEnum
End Select
```

Pomocí **přidejte** rychlé akce vyplnit chybějící případech i v případě výchozí vytvoří následující:

```csharp
switch(myEnum)
{
    case MyEnum.Item1:
        break;
    case MyEnum.Item2:
        break;
    case MyEnum.Item3:
        break;
    default:
        break;
}
```

```vb
Select Case myEnum
    Case MyEnum.Item1
        Exit Select
    Case MyEnum.Item2
        Exit Select
    Case Else
        Exit Select
End Select
```

### <a name="correct-misspelled-type"></a>Překlepu správný typ.

Pokud píšete omylem typu v sadě Visual Studio, tato rychlé akce bude automaticky opraven ho za vás.  Zobrazí se tyto položky v nabídce žárovky jako  **"změnu '*nesprávně zadaných typů*'do'*opravte typ*' **.  Příklad:

```csharp
// Before
private viod MyMethod()
{
}

// Change 'viod' to 'void'

// After
private void MyMethod()
{
}
```

```vb
' Before
Function MyFunction as Intger
End Function

' Change 'Intger' to 'Integer'

' After
Function MyFunction as Integer
End Function
```

### <a name="remove-unnecessary-cast"></a>Odebrání nepotřebného přetypování

Pokud přetypovat typ na jiný typ, který nevyžaduje přetypování, **odebrání nepotřebného přetypování** položky rychlé akce odebere přetypování z vašeho kódu.

```csharp
// before
int number = (int)3;

// Remove Unnecessary Cast

// after
int number = 3;
```

```vb
' Before
Dim number as Integer = CType(3, Integer)

' Remove Unnecessary Cast

' After
Dim number as Integer = 3
```

### <a name="replace-method-with-property-or-replace-property-with-method"></a>Replace – metoda s vlastností nebo nahradit vlastnost – metoda

Tyto rychlé akce převede metodu na vlastnost, nebo naopak.  Následující příklad ukazuje změnu z metody vlastnosti.  Opačném případě jednoduše Invertovat *před* a *po* oddíly.

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

```vb
Dim MyValue As Integer

' Before
Function GetMyValue() As Integer
    Return MyValue
End Function

' Replace 'GetMyValue' with property

' After
ReadOnly Property MyValue As Integer
    Get
        Return MyValue
    End Get
End Property
```

### <a name="make-method-synchronous"></a>Vytvořte metodu synchronní

Při použití `async` / `Async` – klíčové slovo na metodu, je očekávat, že někde uvnitř této metody `await` / `Await` – klíčové slovo bude použito.  Ale pokud to není tento případ, rychlé akce se zobrazí, umožní vám provádět metodu synchronní odebráním `async` / `Async` – klíčové slovo a změna návratový typ.  Použití **vytvořte metodu synchronní** možnost v nabídce Rychlé akce.

```csharp
// Before
async Task<int> MyAsyncMethod()
{
    return 3;
}

// Make method synchronous

// After
int MyAsyncMethod()
{
    return 3;
}
```

```vb
' Before
Async Function MyAsyncMethod() As Task(Of Integer)
    Return 3
End Function

' Make method synchronous

' After
Function MyAsyncMethod() As Integer
    Return 3
End Function
```

### <a name="make-method-asynchronous"></a>Vytvořte asynchronní metodu

Při použití `await` / `Await` – klíčové slovo uvnitř metody, očekává se, že je metoda sama označeno `async` / `Async` – klíčové slovo.  Ale pokud to není tento případ, rychlé akce se zobrazí, umožní vám provádět asynchronní metodu.  Použití **zkontrolujte asynchronní metody nebo funkce** možnost v nabídce Rychlé akce.

```csharp
// Before
int MyAsyncMethod()
{
    return await Task.Run(...);
}

// Make method synchronous

// After
async Task<int> MyAsyncMethod()
{
    return await Task.Run(...);
}
```

```vb
' Before
Function MyAsyncMethod() as Integer
    Return  Await Task.Run(...)
End Function

' Make method synchronous

' After
Async Function MyAsyncMethod() As Task(Of Integer)
    Return Await Task.Run(...)
End Function
```

### <a name="remove-unnecessary-usingsimports"></a>Odebrání nepotřebných direktiv using nebo importuje

**Odeberte nepotřebné direktiv using nebo importuje** rychlé akce odebere všechny nepoužívané `using` a `Import` příkazů pro aktuální soubor.  Když vyberete tuto položku, importy oboru názvů nepoužívané okamžitě odeberou.

### <a name="add-usingsimports-for-types-in-reference-assemblies-nuget-packages-or-other-types-in-your-solution"></a>Přidání direktiv using nebo importuje pro typy v referenční sestavení, balíčky NuGet nebo jiných typů ve vašem řešení

Použití typů nachází v jiné projekty v řešení zobrazí rychlé akce automaticky, ale ostatní je nutné povolit z **nástroje > Možnosti > C#** nebo **Základní > Upřesnit** karty:

* Navrhněte direktiv using nebo importuje pro typy v referenční sestavení
* Navrhněte direktiv using nebo importuje pro typy v balíčků NuGet

Když je povolené, pokud použijete typ v oboru názvů, který není v současnosti importovaná, ale existuje v referenční sestavení nebo balíček NuGet, vytvoří se příkaz pomocí nebo importovat.

```csharp
// Before
Debug.WriteLine("Hello");

// using System.Diagnostics;

// After
using System.Diagnostics;

Debug.WriteLine("Hello");
```

```vb
' Before
Debug.WriteLine("Hello")

' Imports System.Diagnostics

// After
Imports System.Diagnostics

Debug.WriteLine("Hello")
```

### <a name="convert-to-interpolated-string"></a>Převést na interpolované řetězce

[Interpolované řetězce](/dotnet/csharp/language-reference/keywords/interpolated-strings) jsou snadný způsob, jak express řetězce s vložené proměnné, podobně jako  **[String.Format](https://msdn.microsoft.com/library/system.string.format.aspx)**  metoda.  Tato akce rychlé rozpozná případech, kdy jsou řetězce zřetězených, nebo pomocí **String.Format**a změny využití interpolované řetězce.

```csharp
// Before
int num = 3;
string s = string.Format("My string with {0} in the middle", num);

// Convert to interpolated string

// After
int num = 3;
string s = $"My string with {num} in the middle";
```

```vb
' Before
Dim num as Integer = 3
Dim s as String = String.Format("My string with {0} in the middle", num)

' Convert to interpolated string

' After
Dim num as Integer = 3
Dim s As String = $"My string with {num} in the middle"
```

### <a name="remove-merge-conflict-markers"></a>Odebrání značek konflikt sloučení

Tyto rychlé akce povolit, můžete použít k řešení konfliktů při slučování pomocí "trvá změnu", které odebere konfliktní kódu a značek. (K dispozici pouze v aplikaci Visual Studio 2017 (verze 15.3 - Preview).)

![Refaktoring - vyřešte konflikt sloučení](../ide/media/vside-refactoring-merge-conflicts.png)

### <a name="add-null-checks-for-parameters"></a>Přidat kontroly hodnoty null pro parametry

Tato rychlá akce umožňuje přidat kontrolu ve vašem kódu říct, zda má parametr hodnotu null. (K dispozici pouze v aplikaci Visual Studio 2017 (verze 15.3 - Preview).)

![Refaktoring – přidání hodnotu null.](../ide/media/vside-refactoring-nullcheck.png)

### <a name="constructor-generator-improvements"></a>Vylepšení generátor – konstruktor

Při vytváření konstruktor, tato rychlé akce umožňuje vybrat vlastnosti nebo pole ke generování nebo konstruktoru lze vygenerovat z prázdným textem zprávy. Můžete ji použít i k přidání parametrů do existující konstruktor z webu volání. (K dispozici pouze v aplikaci Visual Studio 2017 (verze 15.3 - Preview).)

![Refaktoring - generování konstruktorů](../ide/media/vside-refactoring-constructors.png)

### <a name="remove-unused-variables"></a>Odebrat nepoužité proměnné

Tato rychlá akce umožňuje odebrat proměnné, které byly deklarovat, ale nikdy použity v kódu. (K dispozici pouze v aplikaci Visual Studio 2017 (verze 15.3 - Preview).)

![Refaktoring – proměnné](../ide/media/vside-refactoring-unusedvars.png)

### <a name="generate-overrides"></a>Generovat přepsání

Tato rychlá akce umožňuje vytvářet přepsání z prázdný řádek ve třídě nebo struktuře. **Vyberte členy** dialogové okno umožňuje výběr členů pro přepsání. (K dispozici pouze v aplikaci Visual Studio 2017 (verze 15.3 - Preview).)

![Refaktoring - přepsání](../ide/media/vside-refactoring-overrides.png)

![Refaktoring - přepsání dialogové okno](../ide/media/vside-refactoring-overrides-dialog.png)

### <a name="change-base-for-numeric-literals"></a>Změna základ pro číselné literály

Tato rychlá akce umožňuje převést číselný literál v jednom základní číselné systému. Můžete například číslo hexadecimální nebo do binárního formátu. (K dispozici pouze v aplikaci Visual Studio 2017 (verze 15.3 - Preview).)

![Refaktoring - změňte základní](../ide/media/vside-refactoring-changebase1.png)

![Refaktoring - změňte základní](../ide/media/vside-refactoring-changebase2.png)

### <a name="insert-digit-separators-into-literals"></a>Vložit číslice oddělovačů do literály

Tato rychlá akce umožňuje přidat znaků oddělujících do literálových hodnot. (K dispozici pouze v aplikaci Visual Studio 2017 (verze 15.3 - Preview).)

![Refaktoring - změna číslice oddělovačů](../ide/media/vside-refactoring-separators.png)

### <a name="convert-if-construct-to-switch"></a>Převést **Pokud** vytvořit k **přepínače**

Tato rychlá akce lze převést **if potom else** vytvořit na **přepínače** vytvořit. (K dispozici pouze v aplikaci Visual Studio 2017 (verze 15.3 - Preview).)

```csharp
// Before
if (obj is string s)
{
  Console.WriteLine("obj is a string: " + s);
}

else if (obj is int i && i > 10)
{
  Console.WriteLine("obj is an int greater than 10");
}

// Convert to switch

// After
switch (obj)
{
  case string s:
    Console.WriteLine("Obj is a string: " + s);
    break;
  case int i when i > 10:
    Console.WriteLine("obj is an int greater than 10");
    break;
}
```

```vb
' Before
If TypeOf obj Is String s Then
    Console.WriteLine("obj is a string: " + s)
Else If TypeOf obj Is Integer i And i > 10 Then
    Console.WriteLine("obj is an int greater than 10")
End If

' Convert to switch

' After
Select Case obj
  Case String s
    Console.WriteLine("Obj is a string: " + s)
    Exit Sub
  Case Integer i when i > 10
    Console.WriteLine("obj is an int greater than 10")
    Exit Sub
End Select
```

## <a name="see-also"></a>Viz také

[Styly kódu a rychlé akce](code-styles-and-quick-actions.md)  
[Psaní a refaktoring kódu (C++)](/cpp/ide/writing-and-refactoring-code-cpp)
