---
title: Kódování nastavení konvence pro EditorConfig v sadě Visual Studio .NET
ms.date: 02/28/2018
ms.topic: reference
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- coding conventions [EditorConfig]
- EditorConfig coding conventions
- language conventions [EditorConfig]
- formatting conventions [EditorConfig]
author: kuhlenh
ms.author: kaseyu
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d4e45283bd65281ea1abc6bad8317379e8341e3c
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
---
# <a name="net-coding-convention-settings-for-editorconfig"></a>Kódování nastavení konvence pro EditorConfig rozhraní .NET

V Visual Studio 2017, můžete definovat a udržovat styl konzistentní kód ve vaší základu kódu s použitím [EditorConfig](../ide/create-portable-custom-editor-options.md) souboru. EditorConfig obsahuje několik jader formátování vlastností, jako například `indent_style` a `indent_size`. V sadě Visual Studio .NET kódování konvence nastavení lze také nakonfigurovat pomocí souboru EditorConfig. Soubory EditorConfig umožňují vám umožní povolit nebo zakázat jednotlivé .NET konvence kódování a nakonfigurovat na úroveň, na který chcete konvence vynucuje prostřednictvím úroveň závažnosti. Další informace o tom, jak zajistit konzistenci v vaší codebase pomocí EditorConfig [vytvoření přenosné vlastního editoru možnosti](../ide/create-portable-custom-editor-options.md). Můžete také zobrazit [platformy .NET kompilátoru .editorconfig soubor](https://github.com/dotnet/roslyn/blob/master/.editorconfig) jako příklad.

Existují tři podporované .NET kódování konvence kategorie:

- [Jazyk konvence](#language-conventions)

   Pravidla týkající se jazyka C# nebo Visual Basic. Například můžete zadat pravidla kolem pomocí `var` nebo explicitních typů, při definování proměnné nebo upřednostňují výraz vozidlo členy.

- [Formátování konvence](#formatting-conventions)

   Pravidla týkající se rozložení a struktura kódu abyste snadněji číst. Například můžete zadat pravidla kolem složené závorky Allman nebo upřednostňují mezery v blocích ovládacího prvku.

- [Zásady vytváření názvů](../ide/editorconfig-naming-conventions.md)

   Pravidla týkající se názvů elementy kódu. Například můžete určit, že `async` metody musí končit "Asynchronní".

## <a name="language-conventions"></a>Jazyk konvence

Pravidla pro jazyk konvence mít následující formát:

`options_name = false|true : none|suggestion|warning|error`

Pro každé pravidlo konvence jazyk, je nutné zadat buď **true** (upřednostnit tento styl) nebo **false** (není přednost tento styl) a **závažnost**. Závažnost určuje úroveň vynucení pro daný styl.

Následující tabulka uvádí možné závažnost hodnoty a jejich důsledky:

Závažnost | Efekt
:------- | ------
žádná nebo tichou | Nezobrazovat nic uživateli při porušení toto pravidlo. Funkce generování kódu vygeneruje kód v tomto stylu, ale.
Návrh | Pokud toto pravidlo stylu je došlo k porušení, je zobrazit uživateli jako návrh. Návrhy se zobrazí jako tři tečky šedé pod první dva znaky.
upozornění | Pokud toto pravidlo stylu je došlo k porušení, zobrazit upozornění kompilátoru.
Chyba | Pokud toto pravidlo stylu je došlo k porušení, zobrazit chyba kompilátoru.

V následujícím seznamu jsou povolená jazyk pravidla konvence:

- Nastavení stylu kódu rozhraní .NET
    - ["This." a kvalifikátory "mě."](#this_and_me)
        - DotNet\_styl\_kvalifikace\_for_field
        - dotnet\_style\_qualification\_for_property
        - DotNet\_styl\_kvalifikace\_for_method
        - DotNet\_styl\_kvalifikace\_for_event
    - [Klíčová slova jazyka namísto názvů typu framework pro odkazy na typ](#language_keywords)
        - DotNet\_styl\_předdefinované\_typ\_pro\_místní hodnoty –\_parameters_members
        - DotNet\_styl\_předdefinované\_typ\_pro\_member_access
    - [Předvolby – modifikátor](#normalize_modifiers)
        - DotNet\_styl\_vyžadují\_accessibility_modifiers
        - csharp\_preferred\_modifier_order
        - visual\_basic\_preferred\_modifier_order
    - [Předvolby úrovni výrazu](#expression_level)
        - DotNet\_styl\_object_initializer
        - DotNet\_styl\_collection_initializer
        - DotNet\_styl\_explicitní\_tuple_names
        - DotNet\_přednost\_odvodit\_tuple_names
        - DotNet\_přednost\_odvodit\_anonymní\_typ\_member_names
    - ["Null" Kontrola předvolby](#null_checking)
        - dotnet\_style\_coalesce_expression
        - dotnet\_style\_null_propagation
- Nastavení stylu kódu C#
    - [Implicitní a explicitní typy](#implicit-and-explicit-types)
        - CSharp\_styl\_var\_pro\_vytvořené\_in_types
        - CSharp\_styl\_var\_při\_typ\_is_apparent
        - csharp\_style\_var_elsewhere
    - [Členové tvoření výrazy](#expression_bodied_members)
        - CSharp\_styl\_výraz\_bodied_methods
        - csharp\_style\_expression\_bodied_constructors
        - csharp\_style\_expression\_bodied_operators
        - csharp\_style\_expression\_bodied_properties
        - csharp\_style\_expression\_bodied_indexers
        - csharp\_style\_expression\_bodied_accessors
    - [Shoda vzoru](#pattern_matching)
        - CSharp\_styl\_vzor\_odpovídající\_přes\_je\_s\_cast_check
        - CSharp\_styl\_vzor\_odpovídající\_přes\_jako\_s\_null_check
    - [Vložená deklarace proměnných](#inlined_variable_declarations)
        - CSharp\_styl\_vložená\_variable_declaration
    - [Předvolby úrovni výrazu](#expression_level_csharp)
        - csharp\_prefer\_simple\_default_expression
        - CSharp\_styl\_deconstructed\_variable_declaration
        - CSharp\_styl\_vzor\_místní\_přes\_anonymous_function
    - ["Null" Kontrola předvolby](#null_checking_csharp)
        - csharp\_style\_throw_expression
        - csharp\_style\_conditional\_delegate_call
    - [Předvolby blok kódu](#code_block)
        - csharp\_prefer_braces

### <a name="net-code-style-settings"></a>Nastavení stylu kódu rozhraní .NET

Pravidla stylu v této části platí pro obě C# a Visual Basic. Pokud chcete zjistit, příklady kódu v preferovaný programovací jazyk, vyberte v rozevíracím seznamu **jazyk** nabídce v pravém horním rohu okna prohlížeče.

#### <a name="this_and_me"></a>"This." a "Me." kvalifikátory.

Toto pravidlo stylu (pravidel ID IDE0003 a IDE0009) můžete použít pro pole, vlastnosti, metody nebo události. Hodnota **true** znamená přednost kódu symbol, který má být uvedena `this.` v jazyce C# nebo `Me.` v jazyce Visual Basic. Hodnota **false** znamená přednost code element _není_ k být uvedena `this.` nebo `Me.`.

Následující tabulka uvádí názvy pravidel, použít programovací jazyky a výchozí hodnoty:

| Název pravidla | Použitelné jazyky | Visual Studio výchozí hodnota |
| ----------- | -------------------- | ----------------------|
| dotnet_style_qualification_for_field | C# a Visual Basic | FALSE: žádné |
| dotnet_style_qualification_for_property | C# a Visual Basic | FALSE: žádné |
| dotnet_style_qualification_for_method | C# a Visual Basic | FALSE: žádné |
| dotnet_style_qualification_for_event | C# a Visual Basic | FALSE: žádné |

**DotNet\_styl\_kvalifikace\_for_field**

- Když je toto pravidlo nastavená na **true**, raději polí, která mají být uvedena `this.` v jazyce C# nebo `Me.` v jazyce Visual Basic.
- Když je toto pravidlo nastavená na **false**, raději pole _není_ k být uvedena `this.` nebo `Me.`.

Příklady kódu:

```csharp
// dotnet_style_qualification_for_field = true
this.capacity = 0;

// dotnet_style_qualification_for_field = false
capacity = 0;
```

```vb
' dotnet_style_qualification_for_field = true
Me.capacity = 0

' dotnet_style_qualification_for_field = false
capacity = 0
```

**dotnet\_style\_qualification\_for_property**

- Když je toto pravidlo nastavená na **true**, raději vlastnosti, které chcete být uvedena `this.` v jazyce C# nebo `Me.` v jazyce Visual Basic.
- Když je toto pravidlo nastavená na **false**, raději vlastnosti _není_ k být uvedena `this.` nebo `Me.`.

Příklady kódu:

```csharp
// dotnet_style_qualification_for_property = true
this.ID = 0;

// dotnet_style_qualification_for_property = false
ID = 0;
```

```vb
' dotnet_style_qualification_for_property = true
Me.ID = 0

' dotnet_style_qualification_for_property = false
ID = 0
```

**DotNet\_styl\_kvalifikace\_for_method**

- Když je toto pravidlo nastavená na **true**, raději metody být uvedena `this.` v jazyce C# nebo `Me.` v jazyce Visual Basic.
- Když je toto pravidlo nastavená na **false**, raději metody _není_ k být uvedena `this.` nebo `Me.`.

Příklady kódu:

```csharp
// dotnet_style_qualification_for_method = true
this.Display();

// dotnet_style_qualification_for_method = false
Display();
```

```vb
' dotnet_style_qualification_for_method = true
Me.Display()

' dotnet_style_qualification_for_method = false
Display()
```

**DotNet\_styl\_kvalifikace\_for_event**

- Když je toto pravidlo nastavená na **true**, raději události, které mají být uvedena `this.` v jazyce C# nebo `Me.` v jazyce Visual Basic.
- Když je toto pravidlo nastavená na **false**, raději události _není_ k být uvedena `this.` nebo `Me.`.

Příklady kódu:

```csharp
// dotnet_style_qualification_for_event = true
this.Elapsed += Handler;

// dotnet_style_qualification_for_event = false
Elapsed += Handler;
```

```vb
' dotnet_style_qualification_for_event = true
AddHandler Me.Elapsed, AddressOf Handler

' dotnet_style_qualification_for_event = false
AddHandler Elapsed, AddressOf Handler
```

Tato pravidla mohou být zobrazeny v *.editorconfig* následujícím způsobem:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_qualification_for_field = false:suggestion
dotnet_style_qualification_for_property = false:suggestion
dotnet_style_qualification_for_method = false:suggestion
dotnet_style_qualification_for_event = false:suggestion
```

#### <a name="language_keywords"></a>Klíčová slova jazyka namísto názvů typu framework pro odkazy na typ

Lokální proměnné, parametry metody a členy třídy, nebo jako samostatné pravidlo na typ člen přístup výrazy, může být použito toto pravidlo stylu. Hodnota **true** znamená přednost klíčové slovo jazyka (například `int` nebo `Integer`) místo názvu typu (například `Int32`) pro typy, které mají klíčové slovo představující je. Hodnota **false** znamená přednost název typu místo klíčové slovo jazyka.

Následující tabulka uvádí názvy pravidel, ID pravidla, použít programovací jazyky a výchozí hodnoty:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio |
| --------- | ------- | -------------------- | ----------------------|
| dotnet_style_predefined_type_for_locals_ parameters_members | IDE0012 a IDE0014 | C# a Visual Basic | hodnotu true: žádné |
| dotnet_style_predefined_type_for_member_access | IDE0013 a IDE0015 | C# a Visual Basic | hodnotu true: žádné |

**DotNet\_styl\_předdefinované\_typ\_pro\_místní hodnoty –\_parameters_members**

- Když je toto pravidlo nastavená na **true**, raději klíčové slovo jazyka pro místní proměnné, parametry metody a členy, místo název typu pro typy, které mají klíčové slovo je zastupovat třídy.
- Když je toto pravidlo nastavená na **false**, raději název typu pro místní proměnné, parametry metody a členy, místo klíčové slovo jazyka třídy.

Příklady kódu:

```csharp
// dotnet_style_predefined_type_for_locals_parameters_members = true
private int _member;

// dotnet_style_predefined_type_for_locals_parameters_members = false
private Int32 _member;
```

```vb
' dotnet_style_predefined_type_for_locals_parameters_members = true
Private _member As Integer

' dotnet_style_predefined_type_for_locals_parameters_members = false
Private _member As Int32
```

**DotNet\_styl\_předdefinované\_typ\_pro\_member_access**

- Když je toto pravidlo nastavená na **true**, raději klíčové slovo jazyka pro člen přístup výrazy, místo název typu pro typy, které mají klíčové slovo představující je.
- Když je toto pravidlo nastavená na **false**, raději název typu pro člen přístup výrazy, místo klíčové slovo jazyka.

Příklady kódu:

```csharp
// dotnet_style_predefined_type_for_member_access = true
var local = int.MaxValue;

// dotnet_style_predefined_type_for_member_access = false
var local = Int32.MaxValue;
```

```vb
' dotnet_style_predefined_type_for_member_access = true
Dim local = Integer.MaxValue

' dotnet_style_predefined_type_for_member_access = false
Dim local = Int32.MaxValue
```

Tato pravidla mohou být zobrazeny v *.editorconfig* následujícím způsobem:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
dotnet_style_predefined_type_for_member_access = true:suggestion
```

#### <a name="normalize_modifiers"></a>Předvolby – modifikátor

Pravidla stylu v této části problém modifikátor předvolby včetně nutnosti modifikátory dostupnosti a určení požadované modifikátor pořadí řazení.

Následující tabulka uvádí názvy pravidel, pravidlo ID, použít programovacích jazyků, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| dotnet_style_require_ accessibility_modifiers | IDE0040 | C# a Visual Basic | for_non_interface_members:none | 15.5 |
| csharp_preferred_modifier_order | IDE0036 | C# | veřejné, privátní, chráněné, interní, statické, extern, nové, virtuální, abstraktní a uzavřené, přepsání, jen pro čtení, unsafe, volatile, asynchronní: žádné | 15.5 |
| visual_basic_preferred_modifier_order | IDE0036 | Visual Basic | Partial, výchozí, privátní, chráněný, veřejné, přítele, NotOverridable, přepisovatelné, MustOverride, přetížení, přepsání, MustInherit, NotInheritable, statické, sdílené, stínů, jen pro čtení, WriteOnly, dimenze, Const, WithEvents, rozšíření, zužující, vlastní, Asynchronní: žádné | 15.5 |

**DotNet\_styl\_vyžadují\_accessibility_modifiers**

Toto pravidlo nepřijímá **true** nebo **false** hodnoty; místo toho přijímá hodnotu z v následující tabulce:

| Hodnota | Popis |
| ----- |:----------- |
| Vždy | Modifikátory dostupnosti zadat raději |
| pro\_bez\_interface_members | Dáváte přednost modifikátory dostupnosti deklarovat s výjimkou veřejné rozhraní členy. To nebude aktuálně lišit od **vždy** a bude fungovat jako budoucí kontroly pravopisu systému pro Pokud C# přidá výchozí metody rozhraní. |
| Nikdy | Není dáváte přednost modifikátory dostupnosti zadat |

Příklady kódu:

```csharp
// dotnet_style_require_accessibility_modifiers = always
// dotnet_style_require_accessibility_modifiers = for_non_interface_members
class MyClass
{
    private const string thisFieldIsConst = "constant";
}

// dotnet_style_require_accessibility_modifiers = never
class MyClass
{
    const string thisFieldIsConst = "constant";
}
```

**csharp_preferred_modifier_order**

- Pokud toto pravidlo je nastavená na seznam modifikátory, raději zadaný řazení.
- Pokud toto pravidlo je vynechán ze souboru, není přednost modifikátor pořadí.

Příklady kódu:

```csharp
// csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async
class MyClass
{
    private static readonly int _daysInYear = 365;
}
```

**visual_basic_preferred_modifier_order**

- Pokud toto pravidlo je nastavená na seznam modifikátory, raději zadaný řazení.
- Pokud toto pravidlo je vynechán ze souboru, není přednost modifikátor pořadí.

Příklady kódu:

```vb
' visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async
Public Class MyClass
    Private Shared ReadOnly daysInYear As Int = 365
End Class
```

Tato pravidla mohou být zobrazeny v *.editorconfig* následujícím způsobem:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_require_accessibility_modifiers = always:suggestion

# CSharp code style settings:
[*.cs]
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Visual Basic code style settings:
[*.vb]
visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async:suggestion
```

#### <a name="expression_level"></a>Předvolby úrovni výrazu

Styl pravidla v této části problém výraz úrovni předvolby, včetně použití inicializátory objektů, Inicializátory kolekcí, názvy explicitní nebo vyvozen řazené kolekce členů a anonymní typy odvodit.

Následující tabulka uvádí názvy pravidel, pravidlo ID, použít programovacích jazyků, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_object_initializer | IDE0017 | C# a Visual Basic | hodnotu true: návrh | První verze |
| dotnet_style_collection_initializer | IDE0028 | C# a Visual Basic | hodnotu true: návrh | První verze |
| dotnet_style_explicit_tuple_names | IDE0033 | C# 7.0 + a Visual Basic 15 + | hodnotu true: návrh | První verze |
| dotnet_style_prefer_inferred_tuple_names | IDE0037 | C# 7.1 + a Visual Basic 15 + | hodnotu true: návrh | 15,6 operací |
| dotnet_style_prefer_inferred_anonymous_ type_member_names | IDE0037 | C# a Visual Basic | hodnotu true: návrh | 15,6 operací |

**DotNet\_styl\_object_initializer**

- Když je toto pravidlo nastavená na **true**, raději objekty, které se inicializovat pomocí inicializátory objektů, pokud je to možné.
- Když je toto pravidlo nastavená na **false**, raději objekty, které se *není* být inicializována pomocí inicializátory objektů.

Příklady kódu:

```csharp
// dotnet_style_object_initializer = true
var c = new Customer() { Age = 21 };

// dotnet_style_object_initializer = false
var c = new Customer();
c.Age = 21;
```

```vb
' dotnet_style_object_initializer = true
Dim c = New Customer() With {.Age = 21}

' dotnet_style_object_initializer = false
Dim c = New Customer()
c.Age = 21
```

**DotNet\_styl\_collection_initializer**

- Když je toto pravidlo nastavená na **true**, raději kolekcí, aby bylo možné inicializována pomocí Inicializátory kolekcí, pokud je to možné.
- Když je toto pravidlo nastavená na **false**, raději kolekce a *není* být inicializována pomocí Inicializátory kolekcí.

Příklady kódu:

```csharp
// dotnet_style_collection_initializer = true
var list = new List<int> { 1, 2, 3 };

// dotnet_style_collection_initializer = false
var list = new List<int>();
list.Add(1);
list.Add(2);
list.Add(3);
```

```vb
' dotnet_style_collection_initializer = true
Dim list = New List(Of Integer) From {1, 2, 3}

' dotnet_style_collection_initializer = false
Dim list = New List(Of Integer)
list.Add(1)
list.Add(2)
list.Add(3)
```

**DotNet\_styl\_explicitní\_tuple_names**

- Když je toto pravidlo nastavená na **true**, přednost ItemX vlastnosti názvy řazené kolekce členů.
- Když je toto pravidlo nastavená na **false**, přednost ItemX vlastnosti názvy řazené kolekce členů.

Příklady kódu:

```csharp
// dotnet_style_explicit_tuple_names = true
(string name, int age) customer = GetCustomer();
var name = customer.name;

// dotnet_style_explicit_tuple_names = false
(string name, int age) customer = GetCustomer();
var name = customer.Item1;
```

```vb
 ' dotnet_style_explicit_tuple_names = true
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.name

' dotnet_style_explicit_tuple_names = false
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.Item1
```

**DotNet\_styl\_přednost\_odvodit\_tuple_names**

- Když je toto pravidlo nastavená na **true**, raději názvy elementů odvozené řazené kolekce členů.
- Když je toto pravidlo nastavená na **false**, raději názvy elementů explicitní řazené kolekce členů.

Příklady kódu:

```csharp
// dotnet_style_prefer_inferred_tuple_names = true
var tuple = (age, name);

// dotnet_style_prefer_inferred_tuple_names = false
var tuple = (age: age, name: name);
```

**DotNet\_styl\_přednost\_odvodit\_anonymní\_typ\_member_names**

- Když je toto pravidlo nastavená na **true**, raději názvy člen vyvozen anonymního typu.
- Když je toto pravidlo nastavená na **false**, dáváte přednost explicitní anonymního typu názvy členů.

Příklady kódu:

```csharp
// dotnet_style_prefer_inferred_anonymous_type_member_names = true
var anon = new { age, name };

// dotnet_style_prefer_inferred_anonymous_type_member_names = false
var anon = new { age = age, name = name };

```

Tato pravidla mohou být zobrazeny v *.editorconfig* následujícím způsobem:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
```

#### <a name="null_checking"></a>Kontrola Null předvolby

Pravidla stylu v této části se týkají předvolby kontrola hodnotu null.

Následující tabulka uvádí názvy pravidel, pravidlo ID, použít programovacích jazyků, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_coalesce_expression | IDE0029 | C# a Visual Basic | hodnotu true: návrh | První verze |
| dotnet_style_null_propagation | IDE0031 | C# 6.0 + a Visual Basic 14 + | hodnotu true: návrh | První verze |

**dotnet\_style\_coalesce_expression**

- Když je toto pravidlo nastavená na **true**, raději null slučování výrazy Ternární operátor kontrola.
- Když je toto pravidlo nastavená na **false**, raději Ternární operátor kontrola slučování výrazy hodnotu null.

Příklady kódu:

```csharp
// dotnet_style_coalesce_expression = true
var v = x ?? y;

// dotnet_style_coalesce_expression = false
var v = x != null ? x : y; // or
var v = x == null ? y : x;
```

```vb
' dotnet_style_coalesce_expression = true
Dim v = If(x, y)

' dotnet_style_coalesce_expression = false
Dim v = If(x Is Nothing, y, x) ' or
Dim v = If(x IsNot Nothing, x, y)
```

**dotnet\_style\_null_propagation**

- Když je toto pravidlo nastavená na **true**, dávají přednost používání operátor podmíněného hodnotu null, pokud je to možné.
- Když je toto pravidlo nastavená na **false**, dávají přednost používání Ternární null kontrole, kde je to možné.

Příklady kódu:

```csharp
// dotnet_style_null_propagation = true
var v = o?.ToString();

// dotnet_style_null_propagation = false
var v = o == null ? null : o.ToString(); // or
var v = o != null ? o.String() : null;
```

```vb
' dotnet_style_null_propagation = true
Dim v = o?.ToString()

' dotnet_style_null_propagation = false
Dim v = If(o Is Nothing, Nothing, o.ToString()) ' or
Dim v = If(o IsNot Nothing, o.ToString(), Nothing)
```

Tato pravidla mohou být zobrazeny v *.editorconfig* následujícím způsobem:

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_null_propagation = true:suggestion
```

### <a name="c-code-style-settings"></a>Nastavení stylu kódu C#

Pravidla stylu v této části jsou jenom pro C#.

#### <a name="implicit-and-explicit-types"></a>Implicitní a explicitní typy

Pravidla stylu v této části (pravidel ID IDE0007 a IDE0008) se týkají použití [var](/dotnet/csharp/language-reference/keywords/var) – klíčové slovo versus explicitního typu v deklarace proměnné. Toto pravidlo můžete použít samostatně a vestavěné typy, když je typ zřejmá jinde.

Následující tabulka uvádí názvy pravidel, použít programovací jazyky a výchozí hodnoty:

| Název pravidla | Použitelné jazyky | Výchozí Visual Studio |
| ----------- | -------------------- | ----------------------|
| csharp_style_var_for_built_in_types | C# | hodnotu true: žádné |
| csharp_style_var_when_type_is_apparent | C# | hodnotu true: žádné |
| csharp_style_var_elsewhere | C# | hodnotu true: žádné |

**CSharp\_styl\_var\_pro\_vytvořené\_in_types**

- Když je toto pravidlo nastavená na **true**, raději `var` se používá k deklaraci proměnné pomocí předdefinovaného systémového typy, jako `int`.
- Když je toto pravidlo nastavená na **false**, přednost explicitní typ přes `var` deklarovat proměnné pomocí předdefinovaného systémového typy, jako `int`.

Příklady kódu:

```csharp
// csharp_style_var_for_built_in_types = true
var x = 5;

// csharp_style_var_for_built_in_types = false
int x = 5;
```

**csharp\_style\_var\_when\_type\_is_apparent**

- Když je toto pravidlo nastavená na **true**, raději `var` když je typ již uveden na pravé straně výrazu deklarace.
- Když je toto pravidlo nastavená na **false**, přednost explicitní typ přes `var` když je typ již uveden na pravé straně výrazu deklarace.

Příklady kódu:

```csharp
// csharp_style_var_when_type_is_apparent = true
var obj = new Customer();

// csharp_style_var_when_type_is_apparent = false
Customer obj = new Customer();
```

**csharp\_style\_var_elsewhere**

- Když je toto pravidlo nastavená na **true**, raději `var` přes explicitního typu ve všech případech, není-li přepsat pravidlo stylu jiný kód.
- Když je toto pravidlo nastavená na **false**, přednost explicitní typ přes `var` ve všech případech, není-li přepsat pravidlo stylu jiný kód.

Příklady kódu:

```csharp
// csharp_style_var_elsewhere = true
var f = this.Init();

// csharp_style_var_elsewhere = false
bool f = this.Init();
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
csharp_style_var_when_type_is_apparent = true:suggestion
csharp_style_var_elsewhere = true:suggestion
```

#### <a name="expression_bodied_members"></a>Výraz vozidlo členy

Pravidla stylu v této části se týkají použití [výraz vozidlo členy](/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members) při logiku se skládá z jednoho výrazu. Metody, konstruktory, operátory, vlastnosti, indexery a přístupových objektů může být použito toto pravidlo.

Následující tabulka uvádí názvy pravidel, pravidlo ID, příslušné jazykové verze, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_style_expression_bodied_methods | IDE0022 | C# 6.0 + | FALSE: žádné | 15.3 |
| csharp_style_expression_bodied_constructors | IDE0021 | C# 7.0 + | FALSE: žádné | 15.3 |
| csharp_style_expression_bodied_operators | IDE0023 a IDE0024 | C# 7.0 + | FALSE: žádné | 15.3 |
| csharp_style_expression_bodied_properties | IDE0025 | C# 7.0 + | hodnotu true: žádné | 15.3 |
| csharp_style_expression_bodied_indexers | IDE0026 | C# 7.0 + | hodnotu true: žádné | 15.3 |
| csharp_style_expression_bodied_accessors | IDE0027 | C# 7.0 + | hodnotu true: žádné | 15.3 |

**csharp\_style\_expression\_bodied_methods**

Toto pravidlo je možné zadat hodnoty z v následující tabulce:

| Hodnota | Popis |
| ----- |:----------- |
| true | Dáváte přednost výraz vozidlo členy pro metody |
| when_on_single_line | Dáváte přednost výraz vozidlo členy pro metody, když bude jeden řádek |
| false | Dáváte přednost bloku těla metody |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_methods = true
public int GetAge() => this.Age;

// csharp_style_expression_bodied_methods = false
public int GetAge() { return this.Age; }
```

**csharp\_style\_expression\_bodied_constructors**

Toto pravidlo je možné zadat hodnoty z v následující tabulce:

| Hodnota | Popis |
| ----- |:----------- |
| true | Dáváte přednost výraz vozidlo členy pro konstruktory |
| when_on_single_line | Dáváte přednost výraz vozidlo členy pro konstruktory, když bude jeden řádek |
| false | Dáváte přednost těla bloku pro konstruktory |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_constructors = true
public Customer(int age) => Age = age;

// csharp_style_expression_bodied_constructors = false
public Customer(int age) { Age = age; }
```

**csharp\_style\_expression\_bodied_operators**

Toto pravidlo je možné zadat hodnoty z v následující tabulce:

| Hodnota | Popis |
| ----- |:----------- |
| true | Dáváte přednost výraz vozidlo členy pro operátory |
| when_on_single_line | Dáváte přednost výraz vozidlo členy pro operátory, když bude jeden řádek |
| false | Dáváte přednost těla bloku pro operátory |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_operators = true
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
    => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

// csharp_style_expression_bodied_operators = false
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
```

**csharp\_style\_expression\_bodied_properties**

Toto pravidlo je možné zadat hodnoty z v následující tabulce:

| Hodnota | Popis |
| ----- |:----------- |
| true | Dáváte přednost výraz vozidlo členy pro vlastnosti |
| when_on_single_line | Dáváte přednost výraz vozidlo členy pro vlastnosti, když bude jeden řádek |
| false | Dáváte přednost těla bloku pro vlastnosti |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_properties = true
public int Age => _age;

// csharp_style_expression_bodied_properties = false
public int Age { get { return _age; }}
```

**csharp\_style\_expression\_bodied_indexers**

Toto pravidlo je možné zadat hodnoty z v následující tabulce:

| Hodnota | Popis |
| ----- |:----------- |
| true | Dáváte přednost výraz vozidlo členy pro indexery |
| when_on_single_line | Dáváte přednost výraz vozidlo členy pro indexery, když bude jeden řádek |
| false | Dáváte přednost těla bloku pro indexery |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_indexers = true
public T this[int i] => _value[i];

// csharp_style_expression_bodied_indexers = false
public T this[int i] { get { return _values[i]; } }
```

**csharp\_style\_expression\_bodied_accessors**

Toto pravidlo je možné zadat hodnoty z v následující tabulce:

| Hodnota | Popis |
| ----- |:----------- |
| true | Dáváte přednost výraz vozidlo členy pro přistupující objekty |
| when_on_single_line | Dáváte přednost výraz vozidlo členy pro přistupující objekty, když bude jeden řádek |
| false | Dáváte přednost těla bloku pro přistupující objekty |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_accessors = true
public int Age { get => _age; set => _age = value; }

// csharp_style_expression_bodied_accessors = false
public int Age { get { return _age; } set { _age = value; } }
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:none
csharp_style_expression_bodied_constructors = false:none
csharp_style_expression_bodied_operators = false:none
csharp_style_expression_bodied_properties = true:suggestion
csharp_style_expression_bodied_indexers = true:suggestion
csharp_style_expression_bodied_accessors = true:suggestion
```

#### <a name="pattern_matching"></a>Shoda vzoru

Pravidla stylu v této části se týkají použití [porovnávání vzorů](/dotnet/csharp/pattern-matching) v jazyce C#.

Následující tabulka uvádí názvy pravidel, pravidlo ID, příslušné jazykové verze a výchozí hodnoty:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio |
| --------- | ------- | -------------------- | ----------------------|
| csharp_style_pattern_matching_over_is_with_cast_check | IDE0020 | C# 7.0 + | hodnotu true: návrh |
| csharp_style_pattern_matching_over_as_with_null_check | IDE0019 | C# 7.0 + | hodnotu true: návrh |

**CSharp\_styl\_vzor\_odpovídající\_přes\_je\_s\_cast_check**

- Když je toto pravidlo nastavená na **true**, raději shoda vzoru místo `is` výrazy s typ přetypování.
- Když je toto pravidlo nastavená na **false**, raději `is` výrazy s přetypování typu místo porovnávání vzorů.

Příklady kódu:

```csharp
// csharp_style_pattern_matching_over_is_with_cast_check = true
if (o is int i) {...}

// csharp_style_pattern_matching_over_is_with_cast_check = false
if (o is int) {var i = (int)o; ... }
```

**csharp\_style\_pattern\_matching\_over\_as\_with\_null_check**

- Když je toto pravidlo nastavená na **true**, raději shoda vzoru místo `as` výrazy s hodnotou null kontroly k určení, pokud je něco určitého typu.
- Když je toto pravidlo nastavená na **false**, raději `as` výrazy s kontroly hodnoty null místo k určení, pokud je něco určitého typu porovnávání vzorů.

Příklady kódu:

```csharp
// csharp_style_pattern_matching_over_as_with_null_check = true
if (o is string s) {...}

// csharp_style_pattern_matching_over_as_with_null_check = false
var s = o as string;
if (s != null) {...}
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

#### <a name="inlined_variable_declarations"></a>Vložená deklarace proměnných

Tento styl jestli pravidlo obavy `out` proměnné jsou deklarovány vložené nebo ne. Spuštění v C# 7, můžete [deklarovat proměnnou mimo v seznamu argumentů volání metody](/dotnet/csharp/language-reference/keywords/out-parameter-modifier#calling-a-method-with-an-out-argument), a nikoli v samostatných deklarace proměnné.

Následující tabulka uvádí název pravidla, ID pravidla, příslušné jazykové verze a výchozí hodnoty:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio |
| --------- | -------- | -------------------- | ----------------------|
| csharp_style_inlined_variable_declaration | IDE0018 | C# 7.0 + | hodnotu true: návrh |

**CSharp\_styl\_vložená\_variable_declaration**

- Když je toto pravidlo nastavená na **true**, raději `out` proměnné deklarovat vložené v seznamu argumentů volání metody, pokud je to možné.
- Když je toto pravidlo nastavená na **false**, raději `out` proměnné deklarovat před volání metody.

Příklady kódu:

```csharp
// csharp_style_inlined_variable_declaration = true
if (int.TryParse(value, out int i) {...}

// csharp_style_inlined_variable_declaration = false
int i;
if (int.TryParse(value, out i) {...}
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

#### <a name="expression_level_csharp"></a>Předvolby úrovni výrazu

Pravidla stylu v této části se týkají výraz úrovni předvolby, včetně použití [výchozí výrazy](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference), deconstructed proměnné a místní funkce přes anonymní funkce.

Následující tabulka uvádí název pravidla, ID pravidla, příslušné jazykové verze, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_prefer_simple_default_expression | IDE0034 | C# 7.1 + | hodnotu true: návrh | 15.3 |
| csharp_style_deconstructed_variable_declaration | IDE0042 | C# 7.0 + | hodnotu true: návrh | 15.5 |
| csharp_style_pattern_local_over_anonymous_function | IDE0039 | C# 7.0 + | hodnotu true: návrh | 15.5 |

**csharp\_prefer\_simple\_default_expression**

Toto pravidlo stylu týká pomocí [ `default` literál pro výchozí hodnotu výrazy](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference) při kompilátor může odvodit typ výrazu.

- Když je toto pravidlo nastavená na **true**, raději `default` přes `default(T)`.
- Když je toto pravidlo nastavená na **false**, raději `default(T)` přes `default`.

Příklady kódu:

```csharp
// csharp_prefer_simple_default_expression = true
void DoWork(CancellationToken cancellationToken = default) { ... }

// csharp_prefer_simple_default_expression = false
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }
```

**CSharp\_styl\_deconstructed\_variable_declaration**

- Když je toto pravidlo nastavená na **true**, raději deconstructed deklarace proměnné.
- Když je toto pravidlo nastavená na **false**, není dáváte přednost deconstruction v deklarace proměnných.

Příklady kódu:

```csharp
// csharp_style_deconstructed_variable_declaration = true
var (name, age) = GetPersonTuple();
Console.WriteLine($"{name} {age}");

(int x, int y) = GetPointTuple();
Console.WriteLine($"{x} {y}");

// csharp_style_deconstructed_variable_declaration = false
var person = GetPersonTuple();
Console.WriteLine($"{person.name} {person.age}");

(int x, int y) point = GetPointTuple();
Console.WriteLine($"{point.x} {point.y}");
```

**CSharp\_styl\_vzor\_místní\_přes\_anonymous_function**

- Když je toto pravidlo nastavená na **true**, raději lokální funkce přes anonymní funkce.
- Když je toto pravidlo nastavená na **false**, raději anonymní funkce přes místní funkce.

Příklady kódu:

```csharp
// csharp_style_pattern_local_over_anonymous_function = true
int fibonacci(int n)
{
    return n <= 1 ? 1 : fibonacci(n-1) + fibonacci(n-2);
}

// csharp_style_pattern_local_over_anonymous_function = false
Func<int, int> fibonacci = null;
fibonacci = (int n) =>
{
    return n <= 1 ? 1 : fibonacci(n - 1) + fibonacci(n - 2);
};
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
```

#### <a name="null_checking_csharp"></a>"Null" Kontrola předvolby

Tyto potíže pravidla styl syntaxe kolem `null` kontrola, včetně použití `throw` výrazy nebo `throw` příkazy a zda chcete provést kontrolu hodnotu null nebo použít podmíněný operátor slučování (`?.`) při vyvolání [výrazu lambda](/dotnet/csharp/lambda-expressions).

Následující tabulka uvádí názvy pravidel, pravidlo ID, příslušné jazykové verze a výchozí hodnoty:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio |
| --------- | ------- | -------------------- | ----------------------|
| csharp_style_throw_expression | IDE0016 | C# 7.0 + | hodnotu true: návrh |
| csharp_style_conditional_delegate_call | IDE0041 | C# 6.0 + | hodnotu true: návrh |

**csharp\_style\_throw_expression**

- Když je toto pravidlo nastavená na **true**, dávají přednost používání `throw` výrazy místo `throw` příkazy.
- Když je toto pravidlo nastavená na **false**, dávají přednost používání `throw` příkazy místo `throw` výrazy.

Příklady kódu:

```csharp
// csharp_style_throw_expression = true
this.s = s ?? throw new ArgumentNullException(nameof(s));

// csharp_style_throw_expression = false
if (s == null) { throw new ArgumentNullException(nameof(s)); }
this.s = s;
```

**csharp\_style\_conditional\_delegate_call**

- Když je toto pravidlo nastavená na **true**, dávají přednost používání podmíněný operátor slučování (`?.`) při vyvolání výrazu lambda, namísto provádění null zkontrolovat.
- Když je toto pravidlo nastavená na **false**, raději provést kontrolu null před vyvoláním výrazu lambda, místo použití podmíněný operátor slučování (`?.`).

Příklady kódu:

```csharp
// csharp_style_conditional_delegate_call = true
func?.Invoke(args);

// csharp_style_conditional_delegate_call = false
if (func != null) { func(args); }
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
csharp_style_conditional_delegate_call = false:suggestion
```

#### <a name="code_block"></a>Předvolby blok kódu

Toto pravidlo stylu týká použití složené závorky `{ }` k obklopit bloky kódu.

Následující tabulka uvádí název pravidla, ID pravidla, příslušné jazykové verze, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | ID pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_prefer_braces | IDE0011 | C# | hodnotu true: žádné | 15.3 |

**csharp\_prefer\_braces**

- Když je toto pravidlo nastavená na **true**, raději složené závorky i pro jeden řádek kódu.
- Když je toto pravidlo nastavená na **false**, dáváte přednost žádné složené závorky, pokud povolena.

Příklady kódu:

```csharp
// csharp_prefer_braces = true
if (test) { this.Display(); }

// csharp_prefer_braces = false
if (test) this.Display();
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:none
```

## <a name="formatting-conventions"></a>Formátování konvence

Většiny pravidel pro formátování konvence mít následující formát:

`rule_name = false|true`

Zadejte buď **true** (upřednostnit tento styl) nebo **false** (není raději tento styl). Nezadávejte žádné závažnosti. Pro několik pravidel, místo hodnotu true nebo false zadejte jiných hodnot na popisují, kdy a kam chcete pravidlo použít.

V následujícím seznamu jsou k dispozici v sadě Visual Studio pravidla formátování konvence:

- Nastavení formátování rozhraní .NET
    - [Uspořádat Using](#usings)
        - dotnet_sort_system_directives_first
- Nastavení formátování C#
    - [Možnosti pro nový řádek](#newline)
        - csharp_new_line_before_open_brace
        - csharp_new_line_before_else
        - csharp_new_line_before_catch
        - csharp_new_line_before_finally
        - csharp_new_line_before_members_in_object_initializers
        - csharp_new_line_before_members_in_anonymous_types
        - csharp_new_line_between_query_expression_clauses
    - [Možnosti odsazení](#indent)
        - csharp_indent_case_contents
        - csharp_indent_switch_labels
        - csharp_indent_labels
    - [Možnosti mezery](#spacing)
        - csharp_space_after_cast
        - csharp_space_after_keywords_in_control_flow_statements
        - csharp_space_between_method_declaration_parameter_list_parentheses
        - csharp_space_between_method_call_parameter_list_parentheses
        - csharp_space_between_parentheses
    - [Možnosti zabalení](#wrapping)
        - csharp_preserve_single_line_statements
        - csharp_preserve_single_line_blocks

### <a name="net-formatting-settings"></a>Nastavení formátování rozhraní .NET

Pravidla formátování v této části se vztahují na C# a Visual Basic.

#### <a name="usings"></a>Uspořádat Using

Toto pravidlo formátování týká umístění System.* pomocí direktiv s ohledem na jiné pomocí direktivy.

Následující tabulka uvádí název pravidla, použitelné jazyky, výchozí hodnota a první podporovanou verzi sady Visual Studio:

| Název pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| ----------- | -------------------- | ----------------------| ----------------  |
| dotnet_sort_system_directives_first |  C# a Visual Basic | true | 15.3  |

**dotnet\_sort\_system\_directives_first**

- Když je toto pravidlo nastavená na **true**System.* pomocí direktiv abecedně seřadí a umístit je před jiné direktiv Using.
- Když je toto pravidlo nastavená na **false**, neumísťujte System.* pomocí direktiv před ostatními pomocí direktivy.

Příklady kódu:

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

Příklad *.editorconfig* souboru:

```EditorConfig
# .NET formatting settings:
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
```

### <a name="c-formatting-settings"></a>Nastavení formátování C#

Pravidla formátování v této části se vztahují pouze na kód C#.

#### <a name="newline"></a>Možnosti pro nový řádek

Tato pravidla formátování týkají použití nové řádky k formátování kódu.

V následující tabulce jsou uvedeny "nový řádek" názvy pravidel, použitelné jazyky, výchozí hodnoty a nejprve podporovaná verze sady Visual Studio:

| Název pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_new_line_before_open_brace |  C# | všechny | 15.3  |
| csharp_new_line_before_else |  C# | true | 15.3  |
| csharp_new_line_before_catch |  C# | true | 15.3  |
| csharp_new_line_before_finally |  C# | true | 15.3  |
| csharp_new_line_before_members_in_object_initializers |  C# | true | 15.3  |
| csharp_new_line_before_members_in_anonymous_types |  C# | true | 15.3  |
| csharp_new_line_between_query_expression_clauses |  C# | true | 15.3  |

**csharp\_new\_line\_before\_open_brace**

Toto pravidlo se vztahuje, zda otevřete levá složená závorka `{` musí být umístěny na stejném řádku jako předchozí kód, nebo na nový řádek. Pro toto pravidlo nezadáte **true** nebo **false**. Místo toho zadejte **všechny**, **žádné**, nebo jeden nebo více code prvky, jako **metody** nebo **vlastnosti**, můžete definovat, kdy by měla být toto pravidlo použít. Úplný seznam povolených hodnot je uvedené v následující tabulce:

| Hodnota | Popis
| ------------- |:-------------|
| přístupové objekty, anonymous_methods, anonymous_types, control_blocks, události, indexery, lambdas, local_functions, metody, object_collection, vlastnosti, typy.<br>(Pro typy víc, oddělujte ','). | Vyžadovat složených závorek, aby se na nový řádek pro zadaný kód elementy (také označované jako "Allman" styl) |
| všechny | Vyžadovat složených závorek, aby se na nový řádek pro všechny výrazy (styl "Allman") |
| žádná | Vyžadovat složených závorek, aby se na stejném řádku pro všechny výrazy ("tisíc & R") |

Příklady kódu:

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

**csharp\_new\_line\_before_else**

- Když je toto pravidlo nastavená na **true**, umístěte `else` příkazy na nový řádek.
- Když je toto pravidlo nastavená na **false**, umístěte `else` příkazy na stejném řádku.

Příklady kódu:

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

**csharp\_new\_line\_before_catch**

- Když je toto pravidlo nastavená na **true**, umístěte `catch` příkazy na nový řádek.
- Když je toto pravidlo nastavená na **false**, umístěte `catch` příkazy na stejném řádku.

Příklady kódu:

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

**csharp\_new\_line\_before_finally**

- Když je toto pravidlo nastavená na **true**, vyžadují `finally` příkazy, čímž se po pravé složené závorce na nový řádek.
- Když je toto pravidlo nastavená na **false**, vyžadují `finally` příkazy na stejném řádku jako složená závorka.

Příklady kódu:

```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

**csharp\_new\_line\_before\_members\_in\_object_initializers**

- Když je toto pravidlo nastavená na **true**, aby členové intiializers objektu na samostatné řádky.
- Když je toto pravidlo nastavená na **false**, vyžadují členy inicializátory objektů na stejném řádku.

Příklady kódu:

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

**csharp\_new\_line\_before\_members\_in\_anonymous_types**

- Když je toto pravidlo nastavená na **true**, aby členové anonymní typy na samostatné řádky.
- Když je toto pravidlo nastavená na **false**, vyžadují členů anonymní typy na stejném řádku.

Příklady kódu:

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

**csharp_new_line_between_query_expression_clauses**

- Když je toto pravidlo nastavená na **true**, vyžadují elementy klauzule výraz dotazu na samostatné řádky.
- Když je toto pravidlo nastavená na **false**, vyžadují elementy klauzule výraz dotazu na stejném řádku.

Příklady kódu:

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### <a name="indent"></a>Možnosti odsazení

Tato pravidla formátování týkají použití odsazení formát kódu.

Následující tabulka uvádí názvy pravidel, použitelné jazyky, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_indent_case_contents |  C# | true | 15.3  |
| csharp_indent_switch_labels |  C# | true | 15.3  |
| csharp_indent_labels |  C# | no_change | 15.3  |

**csharp\_indent\_case_contents**

- Když je toto pravidlo nastavená na **true**, odsazení `switch` případ obsah.
- Když je toto pravidlo nastavená na **false**, není odsazovat `switch` případ obsah.

Příklady kódu:

```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

**csharp\_indent\_switch_labels**

- Když je toto pravidlo nastavená na **true**, odsazení `switch` popisky.
- Když je toto pravidlo nastavená na **false**, není odsazovat `switch` popisky.

Příklady kódu:

```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

**csharp\_indent_labels**

Toto pravidlo nepřijímá **true** nebo **false** hodnoty; místo toho přijímá hodnotu z v následující tabulce:

| Hodnota | Popis |
| ----- |:----------- |
| flush_left | Popisky jsou umístěny v levém sloupci |
| one_less_than_current | Popisky jsou umístěny v některém menší odsazení do aktuálního kontextu |
| no_change | Popisky jsou umístěny na stejném odsazení jako aktuální kontext |

Příklady kódu:

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
```

#### <a name="spacing"></a>Možnosti mezery

Tato pravidla formátování týkají znaky místa k formátování kódu.

Následující tabulka uvádí názvy pravidel, použitelné jazyky, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_space_after_cast |  C# | false | 15.3  |
| csharp_space_after_keywords_in_control_flow_statements |  C# | true | 15.3  |
| csharp_space_between_method_declaration_parameter_ list_parentheses |  C# | false | 15.3  |
| csharp_space_between_method_call_parameter_list_parentheses |  C# | false | 15.3  |
| csharp_space_between_parentheses |  C# | false | 15.3  |

**csharp\_space\_after_cast**

- Když je toto pravidlo nastavená na **true**, vyžadují mezeru mezi přetypování a hodnotou.
- Když je toto pravidlo nastavená na **false**, vyžadují _žádné_ mezery mezi přetypování a hodnotu.

Příklady kódu:

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

**csharp_space_after_keywords_in_control_flow_statements**

- Když je toto pravidlo nastavená na **true**, mezeru po klíčové slovo v příkazu toku řízení například vyžadovat `for` smyčky.
- Když je toto pravidlo nastavená na **false**, vyžadují _žádné_ například místo po klíčové slovo v příkazu toku řízení `for` smyčky.

Příklady kódu:

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

**csharp_space_between_method_declaration_parameter_list_parentheses**

- Když je toto pravidlo nastavená na **true**, umístěte znak mezery po levé závorky a před uzavírací kulatá závorka seznamu Metoda deklarace parametru.
- Když je toto pravidlo nastavená na **false**, neumísťujte místo znaků po levé závorky a před uzavírací kulatá závorka metoda deklarace parametr seznamu.

Příklady kódu:

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

**csharp_space_between_method_call_parameter_list_parentheses**

- Když je toto pravidlo nastavená na **true**, umístěte znak mezery po levé závorky a před uzavírací kulatá závorka volání metody.
- Když je toto pravidlo nastavená na **false**, neumísťujte místo znaků po levé závorky a před uzavírací kulatá závorka volání metody.

Příklady kódu:

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

**csharp_space_between_parentheses**

Toto pravidlo je možné zadat jednu nebo více hodnot v následující tabulce:

| Hodnota | Popis |
| ----- |:------------|
| control_flow_statements | Umístěte mezery mezi závorkách příkazy toku řízení |
| výrazy | Umístěte mezery mezi závorkách výrazů |
| type_casts | Umístěte mezery mezi závorkami v přetypování typu |

Pokud vynecháte toto pravidlo, nebo použít hodnotu s jinými než `control_flow_statements`, `expressions`, nebo `type_casts`, není použita nastavení.

Příklady kódu:

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_parentheses = control_flow_statements, type_casts
```

#### <a name="wrapping"></a>Možnosti zabalení

Tato pravidla formátování týkají použití jedné řádky versus samostatné řádky pro příkazy a bloky kódu.

Následující tabulka uvádí názvy pravidel, použitelné jazyky, výchozí hodnoty a první podporovanou verzi sady Visual Studio:

| Název pravidla | Použitelné jazyky | Výchozí Visual Studio | Visual Studio 2017 verze |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_preserve_single_line_statements |  C# | true | 15.3  |
| csharp_preserve_single_line_blocks |  C# | true | 15.3  |

**csharp_preserve_single_line_statements**

- Když je toto pravidlo nastavená na **true**, nechte příkazy a člen deklarace na stejném řádku.
- Když je toto pravidlo nastavená na **false**, nechte příkazy a člen deklarace na různé řádky.

Příklady kódu:

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

**csharp_preserve_single_line_blocks**

- Když je toto pravidlo nastavená na **true**, nechte blok kódu na jeden řádek.
- Když je toto pravidlo nastavená na **false**, nechte blok kódu na samostatné řádky.

Příklady kódu:

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

Příklad *.editorconfig* souboru:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

## <a name="see-also"></a>Viz také

- [Rychlé akce](../ide/quick-actions.md)
- [Zásady vytváření názvů .NET pro EditorConfig](../ide/editorconfig-naming-conventions.md)
- [Vytvoření přenosné vlastního editoru možnosti](../ide/create-portable-custom-editor-options.md)
- [Soubor .editorconfig platformy .NET kompilátoru](https://github.com/dotnet/roslyn/blob/master/.editorconfig)
