---
title: Konvence jazyk .NET pro EditorConfig
ms.date: 06/17/2019
ms.topic: reference
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- language code style rules [EditorConfig]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 90c080b62be8f3aba128b26aafe9d2b6e30446f5
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2019
ms.locfileid: "67586778"
---
# <a name="language-conventions"></a>Konvence jazyka

Jazykové konvence pro EditorConfig v sadě Visual Studio se dělí do dvou kategorií:

- [Nastavení stylu kódu .NET](#net-code-style-settings)

- [Nastavení stylu kódu C#](#c-code-style-settings)

> [!TIP]
> Pokud chcete zobrazit příklady kódu ve vašem preferovaném programovacím jazyce, zvolte ho pomocí nástroje pro výběr jazyka v pravém horním rohu okna prohlížeče.

## <a name="rule-format"></a>Pravidla formátu

Pravidla pro vytváření názvů jazyka mají následující obecný formát:

`option_name = value:severity`

Pro každý jazyk konvence zadejte hodnotu, která definuje, jestli nebo kdy se má přednost styl. Mnoho pravidel přijmout hodnotu `true` (preferovat tímto stylem) nebo `false` (nepreferovat tímto stylem); ostatní, jako přijmout hodnoty `when_on_single_line` nebo `never`. Druhá část pravidlo určuje **závažnost**.

### <a name="severity"></a>severity

Závažnost konvence jazyk určuje úroveň, kde k vynucení stylu. Následující tabulka uvádí možné závažnost hodnoty a jejich důsledky:

severity | Efekt
:------- | ------
`none` | Nezobrazovat nic uživateli při porušení tohoto pravidla. Funkce generování kódu ale generování kódu v tomto stylu. Pravidla s `none` závažnost nikdy objeví v **rychlé akce a Refaktoringy** nabídky. Ve většině případů to považován za "zakázáno" nebo "ignoruje".
`silent` (také `refactoring` v sadě Visual Studio 2017 verze 15,8 a novější) | Nezobrazovat nic uživateli při porušení tohoto pravidla. Funkce generování kódu ale generování kódu v tomto stylu. Pravidla s `silent` závažnost účastnit vyčištění stejně jako se zobrazí v **rychlé akce a Refaktoringy** nabídky.
`suggestion` | Při porušení tohoto pravidla stylu, zobrazí se uživateli jako návrh. Návrhy jeví jako tři šedé tečky v prvních dvou znacích.
`warning` | Při porušení tohoto pravidla stylu zobrazení upozornění kompilátoru.
`error` | Při porušení tohoto pravidla stylu, zobrazit chybu kompilátoru.

## <a name="net-code-style-settings"></a>Nastavení stylu kódu .NET

Pravidla stylu v této části se vztahují na C# i Visual Basic.

- ["This." a "Me." kvalifikátory](#this-and-me)
   - DotNet\_styl\_kvalifikace\_for_field
   - dotnet\_style\_qualification\_for_property
   - DotNet\_styl\_kvalifikace\_for_method
   - DotNet\_styl\_kvalifikace\_for_event
- [Klíčová slova jazyka místo framework názvy typů pro odkazy na typ](#language-keywords)
   - DotNet\_styl\_předdefinované\_typ\_pro\_lokální\_parameters_members
   - dotnet\_style\_predefined\_type\_for\_member_access
- [Modifikátor předvolby](#normalize-modifiers)
   - dotnet\_style\_require\_accessibility_modifiers
   - csharp\_preferred\_modifier_order
   - visual\_basic\_preferred\_modifier_order
   - dotnet\_style\_readonly\_field
- [Předvolby závorky](#parentheses-preferences)
   - DotNet\_styl\_závorky\_v\_aritmetické\_binární\_operátory
   - DotNet\_styl\_závorky\_v\_jiných\_binární\_operátory
   - DotNet\_styl\_závorky\_v\_jiných\_operátory
   - DotNet\_styl\_závorky\_v\_relační\_binární\_operátory
- [Předvolby výrazu úrovni](#expression-level-preferences)
   - dotnet\_style\_object_initializer
   - DotNet\_styl\_collection_initializer
   - dotnet\_style\_explicit\_tuple_names
   - dotnet\_style\_prefer\_inferred\_tuple_names
   - DotNet\_styl\_raději\_odvodit\_anonymní\_typ\_member_names
   - dotnet\_style\_prefer\_auto\_properties
   - DotNet\_styl\_raději\_je\_null\_zkontrolujte\_přes\_odkaz\_rovnosti\_– metoda
   - DotNet\_styl\_raději\_podmíněného\_výraz\_přes\_přiřazení
   - DotNet\_styl\_raději\_podmíněného\_výraz\_přes\_vrátit
- ["Null" Kontrola předvolby](#null-checking-preferences)
   - dotnet\_style\_coalesce_expression
   - dotnet\_style\_null_propagation

### <a name="this-and-me"></a>"This." a "Me." Kvalifikátory

Toto pravidlo stylu je použít na pole, vlastnosti, metody nebo události. Hodnota **true** znamená, že raději symbol kódu, chcete-li být uvozena řetězcem `this.` v jazyce C# nebo `Me.` v jazyce Visual Basic. Hodnota **false** znamená, že raději prvek kódu _není_ Chcete-li být uvozena řetězcem `this.` nebo `Me.`.

Tato pravidla mohou být zobrazeny v *.editorconfig* to následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_qualification_for_field = false:suggestion
dotnet_style_qualification_for_property = false:suggestion
dotnet_style_qualification_for_method = false:suggestion
dotnet_style_qualification_for_event = false:suggestion
```

#### <a name="dotnetstylequalificationforfield"></a>DotNet\_styl\_kvalifikace\_for_field

|||
|-|-|
| **Název pravidla** | dotnet_style_qualification_for_field |
| **ID pravidla** | IDE0003 a IDE0009 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději pole být uvozena řetězcem `this.` v C# nebo `Me.` v jazyce Visual Basic<br /><br />`false` -Raději pole _není_ Chcete-li být uvozena řetězcem `this.` nebo `Me.` |
| **Visual Studio default** | `false:silent` |

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

#### <a name="dotnetstylequalificationforproperty"></a>dotnet\_style\_qualification\_for_property

|||
|-|-|
| **Název pravidla** | dotnet_style_qualification_for_property |
| **ID pravidla** | IDE0003 a IDE0009 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Preferovat vlastnosti, které chcete být uvozena řetězcem `this.` v C# nebo `Me.` v jazyce Visual Basic<br /><br />`false` -Preferovat vlastnosti _není_ Chcete-li být uvozena řetězcem `this.` nebo `Me.` |
| **Visual Studio default** | `false:silent` |

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

#### <a name="dotnetstylequalificationformethod"></a>DotNet\_styl\_kvalifikace\_for_method

|||
|-|-|
| **Název pravidla** | dotnet_style_qualification_for_method |
| **ID pravidla** | IDE0003 a IDE0009 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Dáváte přednost metody být uvozena řetězcem `this.` v C# nebo `Me.` v jazyce Visual Basic.<br /><br />`false` -Dáváte přednost metody _není_ Chcete-li být uvozena řetězcem `this.` nebo `Me.`. |
| **Visual Studio default** | `false:silent` |

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

#### <a name="dotnetstylequalificationforevent"></a>DotNet\_styl\_kvalifikace\_for_event

|||
|-|-|
| **Název pravidla** | dotnet_style_qualification_for_event |
| **ID pravidla** | IDE0003 a IDE0009 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději události, které mají být uvozena řetězcem `this.` v C# nebo `Me.` v jazyce Visual Basic.<br /><br />`false` -Raději události _není_ Chcete-li být uvozena řetězcem `this.` nebo `Me.`. |
| **Visual Studio default** | `false:silent` |

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

### <a name="language-keywords"></a>Klíčová slova jazyka místo framework názvy typů pro odkazy na typ

Do místní proměnné, parametry metody a členy třídy, nebo jako samostatné pravidlo zadejte výrazy členského přístupu může být použito toto pravidlo stylu. Hodnota **true** znamená, že raději klíčové slovo jazyka (například `int` nebo `Integer`) namísto názvu typu (například `Int32`) pro typy, které mají klíčové slovo představující je. Hodnota **false** raději znamená, že název typu místo klíčového slova jazyka.

Tato pravidla mohou být zobrazeny v *.editorconfig* to následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
dotnet_style_predefined_type_for_member_access = true:suggestion
```

#### <a name="dotnetstylepredefinedtypeforlocalsparametersmembers"></a>DotNet\_styl\_předdefinované\_typ\_pro\_lokální\_parameters_members

|||
|-|-|
| **Název pravidla** | dotnet_style_predefined_type_for_locals_parameters_members |
| **ID pravidla** | IDE0012 a IDE0014 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději klíčové slovo jazyka pro lokální proměnné, parametry metody a členy třídy, namísto názvu typu, pro typy, které mají klíčové slovo představující je<br /><br />`false` -Raději název typu pro místní proměnné, parametry metody a členy třídy, místo klíčového slova jazyka |
| **Visual Studio default** | `true:silent` |

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

#### <a name="dotnetstylepredefinedtypeformemberaccess"></a>dotnet\_style\_predefined\_type\_for\_member_access

|||
|-|-|
| **Název pravidla** | dotnet_style_predefined_type_for_member_access |
| **ID pravidla** | IDE0013 a IDE0015 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději klíčové slovo jazyka pro výrazy přístupu členů, namísto názvu typu, pro typy, které mají klíčové slovo představující je<br /><br />`false` -Raději název typu pro výrazy přístupu členů, místo klíčového slova jazyka |
| **Visual Studio default** | `true:silent` |

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

### <a name="normalize-modifiers"></a>Modifikátor předvolby

Pravidla stylu v této části se týkají modifikátor předvolby, včetně vyžadování modifikátory, zadávat pořadí řazení požadované modifikátor která vyžaduje modifikátor jen pro čtení.

Tato pravidla mohou být zobrazeny v *.editorconfig* to následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_require_accessibility_modifiers = always:suggestion
dotnet_style_readonly_field = true:warning

# CSharp code style settings:
[*.cs]
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Visual Basic code style settings:
[*.vb]
visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async:suggestion
```

#### <a name="dotnetstylerequireaccessibilitymodifiers"></a>dotnet\_style\_require\_accessibility_modifiers

|||
|-|-|
| **Název pravidla** | dotnet_style_require_accessibility_modifiers |
| **ID pravidla** | IDE0040 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always` -Raději modifikátory zadání.<br /><br />`for_non_interface_members` -Raději modifikátory deklarovat s výjimkou veřejné členy. (To je stejný jako **vždy** a byla přidána kontroly pravopisu budoucnost if C# přidá výchozí metody rozhraní.)<br /><br />`never` -Nepreferovat modifikátory zadání.<br /><br />`omit_if_default` -Raději modifikátory dostupnosti. Chcete-li být zadaný – s výjimkou jsou ve výchozím nastavení modifikátor. |
| **Visual Studio default** | `for_non_interface_members:silent` |
| **Zavedení verze** | Visual Studio 2017 verze 15.5 |

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

#### <a name="csharppreferredmodifierorder"></a>csharp_preferred_modifier_order

|||
|-|-|
| **Název pravidla** | csharp_preferred_modifier_order |
| **ID pravidla** | IDE0036 |
| **Použitelné jazyky** | C# |
| **Hodnoty** | Jeden nebo více C# modifikátory, jako například `public`, `private`, a `protected` |
| **Visual Studio default** | `public, private, protected, internal, static, extern, new, virtual, abstract, sealed, override, readonly, unsafe, volatile, async:silent` |
| **Zavedení verze** | Visual Studio 2017 verze 15.5 |

- Pokud toto pravidlo je nastaven na seznam parametrů, dáváte přednost zadaného pořadí.
- Pokud toto pravidlo je vynechán ze souboru, nepreferovat modifikátor pořadí.

Příklady kódu:

```csharp
// csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async
class MyClass
{
    private static readonly int _daysInYear = 365;
}
```

#### <a name="visualbasicpreferredmodifierorder"></a>visual_basic_preferred_modifier_order

|||
|-|-|
| **Název pravidla** | visual_basic_preferred_modifier_order |
| **ID pravidla** | IDE0036 |
| **Použitelné jazyky** | Visual Basic |
| **Hodnoty** | Jeden nebo více modifikátory jazyka Visual Basic, například `Partial`, `Private`, a `Public` |
| **Visual Studio default** | `Partial, Default, Private, Protected, Public, Friend, NotOverridable, Overridable, MustOverride, Overloads, Overrides, MustInherit, NotInheritable, Static, Shared, Shadows, ReadOnly, WriteOnly, Dim, Const,WithEvents, Widening, Narrowing, Custom, Async:silent` |
| **Zavedení verze** | Visual Studio 2017 verze 15.5 |

- Pokud toto pravidlo je nastaven na seznam parametrů, dáváte přednost zadaného pořadí.
- Pokud toto pravidlo je vynechán ze souboru, nepreferovat modifikátor pořadí.

Příklady kódu:

```vb
' visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async
Public Class MyClass
    Private Shared ReadOnly daysInYear As Int = 365
End Class
```

#### <a name="dotnetstylereadonlyfield"></a>dotnet_style_readonly_field

|||
|-|-|
| **Název pravidla** | dotnet_style_readonly_field |
| **ID pravidla** | IDE0044 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Dáváte přednost, že pole by měly být označené `readonly` (C#) nebo `ReadOnly` (Visual Basic) Pokud jsou pouze přiřazeno vložené, nebo v konstruktoru<br /><br />`false` -Zadat žádná předvolba přes Určuje, zda by měly být označené pole `readonly` (C#) nebo `ReadOnly` (Visual Basic) |
| **Visual Studio default** | `true:suggestion` |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |

Příklady kódu:

```csharp
// dotnet_style_readonly_field = true
class MyClass
{
    private readonly int _daysInYear = 365;
}
```

```vb
' dotnet_style_readonly_field = true
Public Class MyClass
    Private ReadOnly daysInYear As Int = 365
End Class
```

### <a name="parentheses-preferences"></a>Předvolby závorky

Pravidla stylu v této části se týkají předvolby závorky, včetně použití závorek pro aritmetické, relační a ostatní binární operátory.

Tato pravidla mohou být zobrazeny v *.editorconfig* to následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_operators = never_if_unnecessary:silent
```

#### <a name="dotnetstyleparenthesesinarithmeticbinaryoperators"></a>DotNet\_styl\_závorky\_v\_aritmetické\_binary_operators

|||
|-|-|
| **Název pravidla** | dotnet_style_parentheses_in_arithmetic_binary_operators |
| **ID pravidla** | IDE0047 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always_for_clarity` -Raději závorky pro upřesnění aritmetického operátoru (`*`, `/`, `%`, `+`, `-`, `<<`, `>>`, `&`, `^`, `|`) prioritu<br /><br />`never_if_unnecessary` -Nepřejete závorky, pokud aritmetického operátoru (`*`, `/`, `%`, `+`, `-`, `<<`, `>>`, `&`, `^`, `|`) prioritu je zřejmé |
| **Visual Studio default** | `always_for_clarity:silent` |
| **Zavedení verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
var v = a + (b * c);

// dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
var v = a + b * c;
```

```vb
' dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
Dim v = a + (b * c)

' dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
Dim v = a + b * c
```

#### <a name="dotnetstyleparenthesesinrelationalbinaryoperators"></a>DotNet\_styl\_závorky\_v\_relační\_binary_operators

|||
|-|-|
| **Název pravidla** | dotnet_style_parentheses_in_relational_binary_operators |
| **ID pravidla** | IDE0047 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always_for_clarity` -Raději závorky pro upřesnění relační operátor (`>`, `<`, `<=`, `>=`, `is`, `as`, `==`, `!=`) prioritu<br /><br />`never_if_unnecessary` -Nepřejete závorky, pokud relační operátor (`>`, `<`, `<=`, `>=`, `is`, `as`, `==`, `!=`) priorita je zřejmé |
| **Visual Studio default** | `always_for_clarity:silent` |
| **Zavedení verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
var v = (a < b) == (c > d);

// dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
var v = a < b == c > d;
```

```vb
' dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
Dim v = (a < b) = (c > d)

' dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
Dim v = a < b = c > d
```

#### <a name="dotnetstyleparenthesesinotherbinaryoperators"></a>DotNet\_styl\_závorky\_v\_jiných\_binary_operators

|||
|-|-|
| **Název pravidla** | dotnet_style_parentheses_in_other_binary_operators |
| **ID pravidla** | IDE0047 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always_for_clarity` -Raději závorky pro upřesnění ostatních binárních operátorů (`&&`, `||`, `??`) prioritu<br /><br />`never_if_unnecessary` -Nepřejete závorky po ostatních binárních operátorů (`&&`, `||`, `??`) priorita je zřejmé |
| **Visual Studio default** | `always_for_clarity:silent` |
| **Zavedení verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
var v = a || (b && c);

// dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
var v = a || b && c;
```

```vb
' dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
Dim v = a OrElse (b AndAlso c)

' dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
Dim v = a OrElse b AndAlso c
```

#### <a name="dotnetstyleparenthesesinotheroperators"></a>DotNet\_styl\_závorky\_v\_other_operators

|||
|-|-|
| **Název pravidla** | dotnet_style_parentheses_in_other_operators |
| **ID pravidla** | IDE0047 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always_for_clarity` -Raději závorky pro upřesnění priorita operátorů<br /><br />`never_if_unnecessary` -Nepřejete závorky po zřejmé priorita operátorů |
| **Visual Studio default** | `never_if_unnecessary:silent` |
| **Zavedení verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_parentheses_in_other_operators = always_for_clarity
var v = (a.b).Length;

// dotnet_style_parentheses_in_other_operators = never_if_unnecessary
var v = a.b.Length;
```

```vb
' dotnet_style_parentheses_in_other_operators = always_for_clarity
Dim v = (a.b).Length

' dotnet_style_parentheses_in_other_operators = never_if_unnecessary
Dim v = a.b.Length
```

### <a name="expression-level-preferences"></a>Předvolby výrazu úrovni

Styl pravidla v této části problém úrovni výrazu předvolby včetně využití čipu TPM inicializátory objektů, inicializátory kolekce, názvy explicitní nebo odvozený řazené kolekce členů a odvodit anonymních typů.

Tato pravidla mohou být zobrazeny v *.editorconfig* to následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
dotnet_style_prefer_auto_properties = true:silent
dotnet_style_prefer_conditional_expression_over_assignment = true:suggestion
dotnet_style_prefer_conditional_expression_over_return = true:suggestion
```

#### <a name="dotnetstyleobjectinitializer"></a>dotnet\_style\_object_initializer

|||
|-|-|
| **Název pravidla** | dotnet_style_object_initializer |
| **ID pravidla** | IDE0017 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději objekty inicializovat inicializátory objektů, pokud je to možné<br /><br />`false` -Raději objektů *není* být inicializovány pomocí inicializátory objektů |
| **Visual Studio default** | `true:suggestion` |

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

#### <a name="dotnetstylecollectioninitializer"></a>DotNet\_styl\_collection_initializer

|||
|-|-|
| **Název pravidla** | dotnet_style_collection_initializer |
| **ID pravidla** | IDE0028 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Upřednostnit kolekce, které mají být inicializovány pomocí inicializátory kolekce, pokud je to možné<br /><br />`false` -Raději kolekcí *není* být inicializovány pomocí inicializátory kolekce |
| **Visual Studio default** | `true:suggestion` |

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

#### <a name="dotnetstyleexplicittuplenames"></a>dotnet\_style\_explicit\_tuple_names

|||
|-|-|
| **Název pravidla** | dotnet_style_explicit_tuple_names |
| **ID pravidla** | IDE0033 |
| **Použitelné jazyky** | C# 7.0 + a Visual Basic 15 + |
| **Hodnoty** | `true` -Raději názvy řazené kolekce členů ItemX vlastnosti<br /><br />`false` -Preferovat vlastnosti ItemX názvů řazené kolekce členů |
| **Visual Studio default** | `true:suggestion` |

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

#### <a name="dotnetstylepreferinferredtuplenames"></a>dotnet\_style\_prefer\_inferred\_tuple_names

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_inferred_tuple_names |
| **ID pravidla** | IDE0037 |
| **Použitelné jazyky** | C# 7.1 + a Visual Basic 15 + |
| **Hodnoty** | `true` -Raději názvy elementů řazené kolekce členů odvozeného<br /><br />`false` -Raději názvy elementů řazené kolekce členů explicitní |
| **Visual Studio default** | `true:suggestion` |
| **Zavedení verze** | Visual Studio 2017 verze 15.6 |

Příklady kódu:

```csharp
// dotnet_style_prefer_inferred_tuple_names = true
var tuple = (age, name);

// dotnet_style_prefer_inferred_tuple_names = false
var tuple = (age: age, name: name);
```

```vb
' dotnet_style_prefer_inferred_tuple_names = true
Dim tuple = (name, age)

' dotnet_style_prefer_inferred_tuple_names = false
Dim tuple = (name:=name, age:=age)
```

#### <a name="dotnetstylepreferinferredanonymoustypemembernames"></a>DotNet\_styl\_raději\_odvodit\_anonymní\_typ\_member_names

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_inferred_anonymous_type_member_names |
| **ID pravidla** | IDE0037 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději názvy členů anonymního typu<br /><br />`false` -Preferovat explicitní anonymního typu názvy členů |
| **Visual Studio default** | `true:suggestion` |
| **Zavedení verze** | Visual Studio 2017 verze 15.6 |

Příklady kódu:

```csharp
// dotnet_style_prefer_inferred_anonymous_type_member_names = true
var anon = new { age, name };

// dotnet_style_prefer_inferred_anonymous_type_member_names = false
var anon = new { age = age, name = name };
```

```vb
' dotnet_style_prefer_inferred_anonymous_type_member_names = true
Dim anon = New With {name, age}

' dotnet_style_prefer_inferred_anonymous_type_member_names = false
Dim anon = New With {.name = name, .age = age}
```

#### <a name="dotnetstylepreferautoproperties"></a>dotnet\_style\_prefer\_auto\_properties

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_auto_properties |
| **ID pravidla** | IDE0032 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději autoproperties prostřednictvím vlastností s privátní pomocné pole<br /><br />`false` -Přes autoproperties preferovat vlastnosti s privátní pomocné pole |
| **Visual Studio default** | `true:suggestion` |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |

Příklady kódu:

```csharp
// dotnet_style_prefer_auto_properties = true
private int Age { get; }

// dotnet_style_prefer_auto_properties = false
private int age;

public int Age
{
    get
    {
        return age;
    }
}
```

```vb
' dotnet_style_prefer_auto_properties = true
Public ReadOnly Property Age As Integer

' dotnet_style_prefer_auto_properties = false
Private _age As Integer

Public ReadOnly Property Age As Integer
    Get
        return _age
    End Get
End Property
```

#### <a name="dotnetstylepreferisnullcheckoverreferenceequalitymethod"></a>DotNet\_styl\_raději\_je\_null\_zkontrolujte\_přes\_odkaz\_rovnosti\_– metoda

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_is_null_check_over_reference_equality_method |
| **ID pravidla** | IDE0041 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Přednost používání kontrolu hodnot null pomocí porovnávání vzorů přes `object.ReferenceEquals`<br /><br />`false` -Raději `object.ReferenceEquals` přes kontrolu hodnot null s porovnáváním vzorů |
| **Visual Studio default** | `true:suggestion` |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |

Příklady kódu:

```csharp
// dotnet_style_prefer_is_null_check_over_reference_equality_method = true
if (value is null)
    return;

// dotnet_style_prefer_is_null_check_over_reference_equality_method = false
if (object.ReferenceEquals(value, null))
    return;
```

```vb
' dotnet_style_prefer_is_null_check_over_reference_equality_method = true
If value Is Nothing
    Return
End If

' dotnet_style_prefer_is_null_check_over_reference_equality_method = false
If Object.ReferenceEquals(value, Nothing)
    Return
End If
```

#### <a name="dotnetstylepreferconditionalexpressionoverassignment"></a>dotnet\_style\_prefer\_conditional\_expression\_over_assignment

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_conditional_expression_over_assignment |
| **ID pravidla** | IDE0045 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději přiřazení s Ternární podmíněné přes if-else – příkaz<br /><br />`false` -Přes Ternární podmíněné raději přiřazení s if-else – příkaz |
| **Visual Studio default** | `true:suggestion` |
| **Zavedení verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_prefer_conditional_expression_over_assignment = true
string s = expr ? "hello" : "world";

// dotnet_style_prefer_conditional_expression_over_assignment = false
string s;
if (expr)
{
    s = "hello";
}
else
{
    s = "world";
}
```

```vb
' dotnet_style_prefer_conditional_expression_over_assignment = true
Dim s As String = If(expr, "hello", "world")

' dotnet_style_prefer_conditional_expression_over_assignment = false
Dim s As String
If expr Then
    s = "hello"
Else
    s = "world"
End If
```

#### <a name="dotnetstylepreferconditionalexpressionoverreturn"></a>DotNet\_styl\_raději\_podmíněného\_výraz\_over_return

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_conditional_expression_over_return |
| **ID pravidla** | IDE0046 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději návratovými příkazy na používání Ternární podmíněné přes if-else – příkaz<br /><br />`false` -Raději návratovými příkazy na používání přes Ternární podmínka if-else – příkaz |
| **Visual Studio default** | `true:suggestion` |
| **Zavedení verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_prefer_conditional_expression_over_return = true
return expr ? "hello" : "world"

// dotnet_style_prefer_conditional_expression_over_return = false
if (expr)
{
    return "hello";
}
else
{
    return "world";
}
```

```vb
' dotnet_style_prefer_conditional_expression_over_return = true
Return If(expr, "hello", "world")

' dotnet_style_prefer_conditional_expression_over_return = false
If expr Then
    Return "hello"
Else
    Return "world"
End If
```

### <a name="null-checking-preferences"></a>Předvolby kontrol Null

Pravidla stylu v této části se týkají předvolby kontrol null.

Tato pravidla mohou být zobrazeny v *.editorconfig* to následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_null_propagation = true:suggestion
```

#### <a name="dotnetstylecoalesceexpression"></a>dotnet\_style\_coalesce_expression

|||
|-|-|
| **Název pravidla** | dotnet_style_coalesce_expression |
| **ID pravidla** | IDE0029 |
| **Použitelné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true` -Raději null slučovací výrazy Ternární operátor kontroly<br /><br />`false` -Raději tříhodnotový operátor kontrola null slučovací výrazy |
| **Visual Studio default** | `true:suggestion` |

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

#### <a name="dotnetstylenullpropagation"></a>dotnet\_style\_null_propagation

|||
|-|-|
| **Název pravidla** | dotnet_style_null_propagation |
| **ID pravidla** | IDE0031 |
| **Použitelné jazyky** | C# 6.0 + a Visual Basic 14 + |
| **Hodnoty** | `true` -Radši chtěli použít operátor podmíněných null, pokud je to možné<br /><br />`false` -Dávají přednost používání Ternární kontrola null tam, kde je to možné |
| **Visual Studio default** | `true:suggestion` |

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

## <a name="c-code-style-settings"></a>Nastavení stylu kódu C#

Pravidla stylu v této části jsou pouze pro C#.

- [Implicitní a explicitní typy](#implicit-and-explicit-types)
   - csharp\_style\_var\_for\_built\_in_types
   - csharp\_style\_var\_when\_type\_is_apparent
   - csharp\_style\_var_elsewhere
- [Členové tvoření výrazy](#expression-bodied-members)
   - csharp\_style\_expression\_bodied_methods
   - csharp\_style\_expression\_bodied_constructors
   - csharp\_style\_expression\_bodied_operators
   - csharp\_style\_expression\_bodied_properties
   - csharp\_style\_expression\_bodied_indexers
   - csharp\_style\_expression\_bodied_accessors
- [Porovnávání vzorů](#pattern-matching)
   - csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check
   - csharp\_style\_pattern\_matching\_over\_as\_with\_null_check
- [Vložená deklarace proměnné](#inlined-variable-declarations)
   - csharp\_style\_inlined\_variable_declaration
- [Předvolby výrazu úrovni](#expression-level-preferences)
   - csharp\_prefer\_simple\_default_expression
   - csharp\_style\_deconstructed\_variable_declaration
   - CSharp\_styl\_vzor\_místní\_přes\_anonymous_function
- ["Null" Kontrola předvolby](#null-checking-preferences)
   - csharp\_style\_throw_expression
   - csharp\_style\_conditional\_delegate_call
- [Předvolby bloku kódu](#code-block-preferences)
   - csharp\_prefer_braces

### <a name="implicit-and-explicit-types"></a>Implicitní a explicitní typy

Pravidla stylu v této části se týkají používání [var](/dotnet/csharp/language-reference/keywords/var) – klíčové slovo oproti explicitního typu v deklaraci proměnné. Toto pravidlo můžete použít samostatně předdefinovaných typů, když typ je zřejmý a jinde.

Příklad *.editorconfig* souboru:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
csharp_style_var_when_type_is_apparent = true:suggestion
csharp_style_var_elsewhere = true:suggestion
```

#### <a name="csharpstylevarforbuiltintypes"></a>csharp\_style\_var\_for\_built\_in_types

|||
|-|-|
| **Název pravidla** | csharp_style_var_for_built_in_types |
| **ID pravidla** | IDE0007 a IDE0008 |
| **Použitelné jazyky** | C#  |
| **Hodnoty** | `true` -Raději `var` se používá k deklaraci proměnné s typy integrovaných systémů, jako `int`<br /><br />`false` -Preferovat explicitní typ přes `var` pro deklarování proměnných, jako integrovaný systém typů `int` |
| **Visual Studio default** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_var_for_built_in_types = true
var x = 5;

// csharp_style_var_for_built_in_types = false
int x = 5;
```

#### <a name="csharpstylevarwhentypeisapparent"></a>csharp\_style\_var\_when\_type\_is_apparent

|||
|-|-|
| **Název pravidla** | csharp_style_var_when_type_is_apparent |
| **ID pravidla** | IDE0007 a IDE0008 |
| **Použitelné jazyky** | C#  |
| **Hodnoty** | `true` -Raději `var` když typ již uvedeno na pravé straně deklarace výrazu<br /><br />`false` -Preferovat explicitní typ přes `var` když typ již uvedeno na pravé straně deklarace výrazu |
| **Visual Studio default** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_var_when_type_is_apparent = true
var obj = new Customer();

// csharp_style_var_when_type_is_apparent = false
Customer obj = new Customer();
```

#### <a name="csharpstylevarelsewhere"></a>csharp\_style\_var_elsewhere

|||
|-|-|
| **Název pravidla** | csharp_style_var_elsewhere |
| **ID pravidla** | IDE0007 a IDE0008 |
| **Použitelné jazyky** | C#  |
| **Hodnoty** | `true` -Raději `var` přes explicitního typu ve všech případech, pokud není přepsán jiným pravidlem styl kódu<br /><br />`false` -Preferovat explicitní typ přes `var` ve všech případech, pokud není přepsán jiným pravidlem styl kódu |
| **Visual Studio default** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_var_elsewhere = true
var f = this.Init();

// csharp_style_var_elsewhere = false
bool f = this.Init();
```

### <a name="expression-bodied-members"></a>Členové tvoření výrazy

Pravidla stylu v této části se týkají používání [členové tvoření](/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members) při logika se skládá z jediného výrazu. Toto pravidlo lze použít pro metody, konstruktory, operátory, vlastnosti, indexery a přístupové objekty.

Příklad *.editorconfig* souboru:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:silent
csharp_style_expression_bodied_constructors = false:silent
csharp_style_expression_bodied_operators = false:silent
csharp_style_expression_bodied_properties = true:suggestion
csharp_style_expression_bodied_indexers = true:suggestion
csharp_style_expression_bodied_accessors = true:suggestion
```

#### <a name="csharpstyleexpressionbodiedmethods"></a>csharp\_style\_expression\_bodied_methods

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_methods |
| **ID pravidla** | IDE0022 |
| **Použitelné jazyky** | C# 6.0 +  |
| **Hodnoty** | `true` -Raději členy s výrazem v těle metody<br /><br />`when_on_single_line` -Raději členy s výrazem v těle metody při bude se jednat o jeden řádek<br /><br />`false` -Raději těla bloků pro metody |
| **Visual Studio default** | `false:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_methods = true
public int GetAge() => this.Age;

// csharp_style_expression_bodied_methods = false
public int GetAge() { return this.Age; }
```

#### <a name="csharpstyleexpressionbodiedconstructors"></a>csharp\_style\_expression\_bodied_constructors

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_constructors |
| **ID pravidla** | IDE0021 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Raději členové tvoření konstruktorů<br /><br />`when_on_single_line` -Raději s výrazem v těle členy pro konstruktory při bude se jednat o jeden řádek<br /><br />`false` -Raději těla bloků pro konstruktory |
| **Visual Studio default** | `false:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_constructors = true
public Customer(int age) => Age = age;

// csharp_style_expression_bodied_constructors = false
public Customer(int age) { Age = age; }
```

#### <a name="csharpstyleexpressionbodiedoperators"></a>csharp\_style\_expression\_bodied_operators

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_operators |
| **ID pravidla** | IDE0023 a IDE0024 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Raději s výrazem v těle členy pro operátory<br /><br />`when_on_single_line` -Raději členové tvoření operátorů při bude se jednat o jeden řádek<br /><br />`false` -Raději těla bloků pro operátory |
| **Visual Studio default** | `false:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_operators = true
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
    => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

// csharp_style_expression_bodied_operators = false
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
```

#### <a name="csharpstyleexpressionbodiedproperties"></a>csharp\_style\_expression\_bodied_properties

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_properties |
| **ID pravidla** | IDE0025 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Raději s výrazem v těle členy pro vlastnosti<br /><br />`when_on_single_line` -Raději s výrazem v těle členy pro vlastnosti při bude se jednat o jeden řádek<br /><br />`false` -Raději těla bloků pro vlastnosti |
| **Visual Studio default** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_properties = true
public int Age => _age;

// csharp_style_expression_bodied_properties = false
public int Age { get { return _age; }}
```

#### <a name="csharpstyleexpressionbodiedindexers"></a>csharp\_style\_expression\_bodied_indexers

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_indexers |
| **ID pravidla** | IDE0026 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Raději s výrazem v těle členy pro indexery<br /><br />`when_on_single_line` -Raději s výrazem v těle členy pro indexery při bude se jednat o jeden řádek<br /><br />`false` -Raději těla bloků pro indexery |
| **Visual Studio default** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_indexers = true
public T this[int i] => _values[i];

// csharp_style_expression_bodied_indexers = false
public T this[int i] { get { return _values[i]; } }
```

#### <a name="csharpstyleexpressionbodiedaccessors"></a>csharp\_style\_expression\_bodied_accessors

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_accessors |
| **ID pravidla** | IDE0027 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Raději s výrazem v těle členy pro přístupové objekty<br /><br />`when_on_single_line` -Raději členové tvoření pro přistupující objekty při bude se jednat o jeden řádek<br /><br />`false` -Raději těla bloků pro přístupové objekty |
| **Visual Studio default** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_accessors = true
public int Age { get => _age; set => _age = value; }

// csharp_style_expression_bodied_accessors = false
public int Age { get { return _age; } set { _age = value; } }
```

### <a name="pattern-matching"></a>Porovnávání vzorů

Pravidla stylu v této části se týkají používání [porovnávání vzorů](/dotnet/csharp/pattern-matching) v jazyce C#.

Příklad *.editorconfig* souboru:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

#### <a name="csharpstylepatternmatchingoveriswithcastcheck"></a>csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check

|||
|-|-|
| **Název pravidla** | csharp_style_pattern_matching_over_is_with_cast_check |
| **ID pravidla** | IDE0020 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Preferovat porovnávání vzorů místo `is` výrazy s přetypování typu<br /><br />`false` -Raději `is` výrazy s přetypování namísto porovnávání vzorů |
| **Visual Studio default** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_pattern_matching_over_is_with_cast_check = true
if (o is int i) {...}

// csharp_style_pattern_matching_over_is_with_cast_check = false
if (o is int) {var i = (int)o; ... }
```

#### <a name="csharpstylepatternmatchingoveraswithnullcheck"></a>csharp\_style\_pattern\_matching\_over\_as\_with\_null_check

|||
|-|-|
| **Název pravidla** | csharp_style_pattern_matching_over_as_with_null_check |
| **ID pravidla** | IDE0019 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Preferovat porovnávání vzorů místo `as` výrazy s kontroly hodnoty null pro určení, zda je něco určitého typu<br /><br />`false` -Raději `as` výrazy s kontroly hodnoty null namísto porovnávání vzorů pro určení, zda je něco určitého typu |
| **Visual Studio default** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_pattern_matching_over_as_with_null_check = true
if (o is string s) {...}

// csharp_style_pattern_matching_over_as_with_null_check = false
var s = o as string;
if (s != null) {...}
```

### <a name="inlined-variable-declarations"></a>Vložená deklarace proměnné

Tento styl, jestli pravidlo se týká `out` proměnné jsou deklarovaná jako inline nebo ne. Spuštění v jazyce C# 7, můžete [deklarovat proměnnou nejsou v seznamu argumentů volání metody](/dotnet/csharp/language-reference/keywords/out-parameter-modifier#calling-a-method-with-an-out-argument), nikoli v samostatné deklarace proměnné.

#### <a name="csharpstyleinlinedvariabledeclaration"></a>csharp\_style\_inlined\_variable_declaration

|||
|-|-|
| **Název pravidla** | csharp_style_inlined_variable_declaration |
| **ID pravidla** | IDE0018 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Raději `out` proměnné se nedá deklarovat vloženě v seznamu argumentů volání metody, pokud je to možné<br /><br />`false` -Raději `out` proměnné deklarované před voláním metody |
| **Visual Studio default** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_inlined_variable_declaration = true
if (int.TryParse(value, out int i) {...}

// csharp_style_inlined_variable_declaration = false
int i;
if (int.TryParse(value, out i) {...}
```

Příklad *.editorconfig* souboru:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

### <a name="expression-level-preferences"></a>Předvolby výrazu úrovni

Pravidla stylu v této části se týkají předvolby výrazu úrovni, včetně použití [výchozí výrazy](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference), dekonstruovanou proměnné a lokální funkce přes anonymní funkce.

Příklad *.editorconfig* souboru:

```ini
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
```

#### <a name="csharpprefersimpledefaultexpression"></a>csharp\_prefer\_simple\_default_expression

Toto pravidlo stylu se týká použití [ `default` literál pro výrazy s výchozími hodnotami](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference) Když kompilátor může odvodit typ výrazu.

|||
|-|-|
| **Název pravidla** | csharp_prefer_simple_default_expression |
| **ID pravidla** | IDE0034 |
| **Použitelné jazyky** | C# 7.1 +  |
| **Hodnoty** | `true` -Raději `default` přes `default(T)`<br /><br />`false` -Raději `default(T)` přes `default` |
| **Visual Studio default** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_prefer_simple_default_expression = true
void DoWork(CancellationToken cancellationToken = default) { ... }

// csharp_prefer_simple_default_expression = false
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }
```

#### <a name="csharpstyledeconstructedvariabledeclaration"></a>csharp\_style\_deconstructed\_variable_declaration

|||
|-|-|
| **Název pravidla** | csharp_style_deconstructed_variable_declaration |
| **ID pravidla** | IDE0042 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Upřednostňovat dekonstruovanou deklaraci proměnných<br /><br />`false` -Nepreferovat dekonstrukce v deklaracích proměnných |
| **Visual Studio default** | `true:suggestion` |

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

#### <a name="csharpstylepatternlocaloveranonymousfunction"></a>CSharp\_styl\_vzor\_místní\_přes\_anonymous_function

|||
|-|-|
| **Název pravidla** | csharp_style_pattern_local_over_anonymous_function |
| **ID pravidla** | IDE0039 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Raději lokální funkce přes anonymní funkce<br /><br />`false` -Raději anonymní funkce přes místní funkce |
| **Visual Studio default** | `true:suggestion` |

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

### <a name="null-checking-preferences"></a>Předvolby kontrol Null

Tyto obavy pravidla stylu syntaxe kolem `null` kontrolu, včetně použití `throw` výrazy nebo `throw` příkazy a zda chcete provést kontrolu hodnot null, nebo použít podmíněný operátor sloučení (`?.`) při vyvolání [výraz lambda](/dotnet/csharp/lambda-expressions).

Příklad *.editorconfig* souboru:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
csharp_style_conditional_delegate_call = false:suggestion
```

#### <a name="csharpstylethrowexpression"></a>csharp\_style\_throw_expression

|||
|-|-|
| **Název pravidla** | csharp_style_throw_expression |
| **ID pravidla** | IDE0016 |
| **Použitelné jazyky** | C# 7.0 +  |
| **Hodnoty** | `true` -Dávají přednost používání `throw` výrazy místo `throw` příkazy<br /><br />`false` -Dávají přednost používání `throw` příkazy místo `throw` výrazy |
| **Visual Studio default** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_throw_expression = true
this.s = s ?? throw new ArgumentNullException(nameof(s));

// csharp_style_throw_expression = false
if (s == null) { throw new ArgumentNullException(nameof(s)); }
this.s = s;
```

#### <a name="csharpstyleconditionaldelegatecall"></a>csharp\_style\_conditional\_delegate_call

|||
|-|-|
| **Název pravidla** | csharp_style_conditional_delegate_call |
| **ID pravidla** | IDE0041 |
| **Použitelné jazyky** | C# 6.0 +  |
| **Hodnoty** | `true` -najdete použít podmíněný operátor sloučení (`?.`) při vyvolání lambda výraz, takže nemusíte provádět s hodnotou null zkontrolujte<br /><br />`false` – Chcete provést kontrolu hodnot null před vyvoláním lambda výrazu, namísto použití podmíněný operátor sloučení (`?.`) |
| **Visual Studio default** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_conditional_delegate_call = true
func?.Invoke(args);

// csharp_style_conditional_delegate_call = false
if (func != null) { func(args); }
```

### <a name="code-block-preferences"></a>Předvolby bloku kódu

Toto pravidlo stylu se týká použití složené závorky `{ }` ohraničit bloky kódu.

Příklad *.editorconfig* souboru:

```ini
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:silent
```

#### <a name="csharppreferbraces"></a>CSharp\_raději\_složené závorky

|||
|-|-|
| **Název pravidla** | csharp_prefer_braces |
| **ID pravidla** | IDE0011 |
| **Použitelné jazyky** | C# |
| **Hodnoty** | `true` -Preferovat složené závorky i pro jeden řádek kódu<br /><br />`false` -Přednost bez složených závorek v případě, že povoleno |
| **Visual Studio default** | `true:silent` |

Příklady kódu:

```csharp
// csharp_prefer_braces = true
if (test) { this.Display(); }

// csharp_prefer_braces = false
if (test) this.Display();
```

## <a name="see-also"></a>Viz také:

- [Konvence formátování](editorconfig-formatting-conventions.md)
- [Zásady vytváření názvů](editorconfig-naming-conventions.md)
- [EditorConfig nastavení konvence psaní kódu .NET](editorconfig-code-style-settings-reference.md)