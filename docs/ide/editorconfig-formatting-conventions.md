---
title: Formátovacích úmluv .NET pro EditorConfig
ms.date: 06/17/2019
ms.topic: reference
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- formatting conventions [EditorConfig]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3218e819d8f94cf760cdc75d6bfa6d29d0a29568
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67823343"
---
# <a name="formatting-conventions"></a>Konvence formátování

Formátovacích úmluv pro EditorConfig pro sadu Visual Studio se dělí do dvou kategorií:

- [Nastavení formátování rozhraní .NET](#net-formatting-settings)

- [Nastavení formátování C#](#c-formatting-settings)

## <a name="rule-format"></a>Pravidla formátu

Pravidla pro konvence formátování mít následující formát:

`rule_name = value`

Pro mnoho pravidel, můžete zadat buď `true` (preferovat tímto stylem) nebo `false` (nepreferovat tímto stylem) pro `value`. Pro ostatní pravidla, je třeba zadat hodnotu `flush_left` nebo `before_and_after` k popisu, kdy a kde použít pravidlo. Nezadávejte závažnosti.

## <a name="net-formatting-settings"></a>Nastavení formátování rozhraní .NET

Pravidla formátování v této části se vztahují na C# a kód jazyka Visual Basic.

- [Uspořádat direktivy using](#organize-using-directives)
  - dotnet_sort_system_directives_first
  - dotnet_separate_import_directive_groups

### <a name="organize-using-directives"></a>Uspořádat direktivy using

Tato pravidla formátování se týkají řazení a zobrazení `using` direktivy a `Imports` příkazy.

Příklad *.editorconfig* souboru:

```ini
# .NET formatting settings
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = true
```

#### <a name="dotnetsortsystemdirectivesfirst"></a>DotNet\_řazení\_systému\_directives_first

|||
|-|-|
| **Název pravidla** | dotnet_sort_system_directives_first |
| **Použitelné jazyky** | C# a Visual Basic |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Řazení System.* `using` direktivy abecedně a umístit je před dalšími direktiv using.<br /><br />`false` -Neumísťujte System.* `using` direktivy před dalšími `using` direktivy. |
| **Visual Studio default** | `true` |

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

#### <a name="dotnetseparateimportdirectivegroups"></a>dotnet\_separate\_import\_directive\_groups

|||
|-|-|
| **Název pravidla** | dotnet_separate_import_directive_groups |
| **Použitelné jazyky** | C# a Visual Basic |
| **Zavedení verze** | Visual Studio 2017 verze 15.5 |
| **Hodnoty** | `true` -Umístit prázdný řádek mezi `using` skupiny direktiv.<br /><br />`false` -Neumísťujte prázdný řádek mezi `using` skupiny direktiv. |
| **Visual Studio default** | `false` |

Příklady kódu:

```csharp
// dotnet_separate_import_directive_groups = true
using System.Collections.Generic;
using System.Threading.Tasks;

using Octokit;

// dotnet_separate_import_directive_groups = false
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;
```

## <a name="c-formatting-settings"></a>Nastavení formátování C#

Formátování pravidla v této části se vztahují pouze na kód jazyka C#.

- [Možnosti nového řádku](#new-line-options)
  - csharp_new_line_before_open_brace
  - csharp_new_line_before_else
  - csharp_new_line_before_catch
  - csharp_new_line_before_finally
  - csharp_new_line_before_members_in_object_initializers
  - csharp_new_line_before_members_in_anonymous_types
  - csharp_new_line_between_query_expression_clauses
- [Možnosti odsazení](#indentation-options)
  - csharp_indent_case_contents
  - csharp_indent_switch_labels
  - csharp_indent_labels
- [Možnosti pro mezery](#spacing-options)
  - csharp_space_after_cast
  - csharp_space_after_keywords_in_control_flow_statements
  - csharp_space_between_method_declaration_parameter_list_parentheses
  - csharp_space_between_method_call_parameter_list_parentheses
  - csharp_space_between_parentheses
  - csharp_space_before_colon_in_inheritance_clause
  - csharp_space_after_colon_in_inheritance_clause
  - csharp_space_around_binary_operators
  - csharp_space_between_method_declaration_empty_parameter_list_parentheses
  - csharp_space_between_method_call_name_and_opening_parenthesis
  - csharp_space_between_method_call_empty_parameter_list_parentheses
  - csharp_space_after_comma
  - csharp_space_after_dot
- [Zabalení možnosti](#wrap-options)
  - csharp_preserve_single_line_statements
  - csharp_preserve_single_line_blocks

### <a name="new-line-options"></a>Možnosti nového řádku

Tato pravidla formátování se týkají používání nových řádků pro formátování kódu.

Příklad *.editorconfig* souboru:

```ini
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

#### <a name="csharpnewlinebeforeopenbrace"></a>csharp\_new\_line\_before\_open_brace

Toto pravidlo se týká, zda levou složenou závorku `{` by měly být umístěny na stejném řádku jako předchozí kód, nebo na nový řádek. Pro toto pravidlo zadáte **všechny**, **žádný**, nebo jeden nebo více prvky kódu, jako **metody** nebo **vlastnosti**, chcete-li definovat, kdy toto pravidlo bude použito. Chcete-li zadat více prvků kódu, oddělte je čárkou (,).

|||
|-|-|
| **Název pravidla** | csharp_new_line_before_open_brace |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `all` -Požadování složených na nový řádek pro všechny výrazy (styl "Allman").<br /><br />`none` -Požadování složených být na stejném řádku pro všechny výrazy ("K & R").<br /><br />`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` -Požadování složených na nový řádek Zadaný kód – element (styl "Allman"). |
| **Visual Studio default** | `all` |

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

#### <a name="csharpnewlinebeforeelse"></a>csharp\_new\_line\_before_else

|||
|-|-|
| **Název pravidla** | csharp_new_line_before_else |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Umístit `else` příkazy na nový řádek.<br /><br />`false` -Umístit `else` příkazy na stejném řádku. |
| **Visual Studio default** | `true` |

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

#### <a name="csharpnewlinebeforecatch"></a>csharp\_new\_line\_before_catch

|||
|-|-|
| **Název pravidla** | csharp_new_line_before_catch |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Umístit `catch` příkazy na nový řádek.<br /><br />`false` -Umístit `catch` příkazy na stejném řádku. |
| **Visual Studio default** | `true` |

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

#### <a name="csharpnewlinebeforefinally"></a>CSharp\_nové\_řádku\_before_finally

|||
|-|-|
| **Název pravidla** | csharp_new_line_before_finally |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Vyžadují `finally` příkazy následovat pravou složenou závorku na nový řádek.<br /><br />`false` -Vyžadují `finally` příkazy na stejném řádku jako pravou složenou závorku. |
| **Visual Studio default** | `true` |

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

#### <a name="csharpnewlinebeforemembersinobjectinitializers"></a>CSharp\_nové\_řádku\_před\_členy\_v\_object_initializers

|||
|-|-|
| **Název pravidla** | csharp_new_line_before_members_in_object_initializers |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Vyžadují členy inicializátory objektů na samostatných řádcích<br /><br />`false` -Vyžadují členy inicializátory objektů na stejném řádku |
| **Visual Studio default** | `true` |

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

#### <a name="csharpnewlinebeforemembersinanonymoustypes"></a>csharp\_new\_line\_before\_members\_in\_anonymous_types

|||
|-|-|
| **Název pravidla** | csharp_new_line_before_members_in_anonymous_types |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Vyžadují členy anonymních typů na samostatných řádcích<br /><br />`false` -Vyžadují členy anonymních typů na stejném řádku |
| **Visual Studio default** | `true` |

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

#### <a name="csharpnewlinebetweenqueryexpressionclauses"></a>csharp_new_line_between_query_expression_clauses

|||
|-|-|
| **Název pravidla** | csharp_new_line_between_query_expression_clauses |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Vyžadují prvky klauzule dotazového výrazu na samostatných řádcích<br /><br />`false` -Vyžadují prvky klauzule dotazového výrazu na stejném řádku |
| **Visual Studio default** | `true` |

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

### <a name="indentation-options"></a>Možnosti odsazení

Tato pravidla formátování se týkají používání odsazení formátovat kód.

Příklad *.editorconfig* souboru:

```ini
# CSharp formatting settings:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
```

#### <a name="csharpindentcasecontents"></a>csharp\_indent\_case_contents

|||
|-|-|
| **Název pravidla** | csharp_indent_case_contents |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Odsazení `switch` malá a velká obsah<br /><br />`false` -Není odsazení `switch` malá a velká obsah |
| **Visual Studio default** | `true` |

- Pokud toto pravidlo je nastaven na **true**, můžu.
- Pokud toto pravidlo je nastaven na **false**, d.

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

#### <a name="csharpindentswitchlabels"></a>csharp\_indent\_switch_labels

|||
|-|-|
| **Název pravidla** | csharp_indent_switch_labels |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Odsazení `switch` popisky<br /><br />`false` -Není odsazení `switch` popisky |
| **Visual Studio default** | `true` |

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

#### <a name="csharpindentlabels"></a>csharp\_indent_labels

|||
|-|-|
| **Název pravidla** | csharp_indent_labels |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `flush_left` – Popisky jsou umístěny ve sloupci nejvíce vlevo<br /><br />`one_less_than_current` – Popisky jsou umístěny na jednom méně odsazení aktuálního kontextu<br /><br />`no_change` – Popisky jsou umístěny ve stejné odsazení jako aktuální kontext |
| **Visual Studio default** | `no_change` |

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

### <a name="spacing-options"></a>Možnosti pro mezery

Tato pravidla formátování se týkají používání znaky mezery pro formátování kódu.

Příklad *.editorconfig* souboru:

```ini
# CSharp formatting settings:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_parentheses = control_flow_statements, type_casts
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_around_binary_operators = before_and_after
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_between_method_call_empty_parameter_list_parentheses = false
csharp_space_after_comma = true
csharp_space_after_dot = false
```

#### <a name="csharpspaceaftercast"></a>csharp\_space\_after_cast

|||
|-|-|
| **Název pravidla** | csharp_space_after_cast |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Vyžadují mezeru mezi přetypování a hodnota<br /><br />`false` -Vyžadují _žádné_ mezeru mezi přetypování a hodnota |
| **Visual Studio default** | `false` |

Příklady kódu:

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

#### <a name="csharpspaceafterkeywordsincontrolflowstatements"></a>csharp_space_after_keywords_in_control_flow_statements

|||
|-|-|
| **Název pravidla** | csharp_space_after_keywords_in_control_flow_statements |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Vyžadují mezera za klíčovým slovem v řídícím toku příkazů, jako `for` smyčky<br /><br />`false` -Vyžadují _žádné_ mezera za klíčovým slovem v řídícím toku příkazů, jako `for` smyčky |
| **Visual Studio default** | `true` |

Příklady kódu:

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

#### <a name="csharpspacebetweenmethoddeclarationparameterlistparentheses"></a>csharp_space_between_method_declaration_parameter_list_parentheses

|||
|-|-|
| **Název pravidla** | csharp_space_between_method_declaration_parameter_list_parentheses |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Umístíte mezeru za levou (otevírací) a před pravou závorku seznamu parametrů deklarace metod.<br /><br />`false` -Neumísťujte znaky mezery za levou (otevírací) a před pravou závorku seznamu parametrů deklarace metod. |
| **Visual Studio default** | `false` |

Příklady kódu:

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

#### <a name="csharpspacebetweenmethodcallparameterlistparentheses"></a>csharp_space_between_method_call_parameter_list_parentheses

|||
|-|-|
| **Název pravidla** | csharp_space_between_method_call_parameter_list_parentheses |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Umístíte mezeru za levou (otevírací) a před pravou závorku volání metody<br /><br />`false` -Neumísťujte znaky mezery za levou (otevírací) a před pravou závorku volání metody |
| **Visual Studio default** | `false` |

Příklady kódu:

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

#### <a name="csharpspacebetweenparentheses"></a>csharp_space_between_parentheses

|||
|-|-|
| **Název pravidla** | csharp_space_between_parentheses |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `control_flow_statements` -Umístit mezeru mezi závorky řídícího toku výrazů<br /><br />`expressions` -Umístit mezeru mezi závorky výrazů<br /><br />`type_casts` -Umístit mezeru mezi závorky v přetypování typu |
| **Visual Studio default** | `false` |

Pokud můžete vynechat, nechte toto pravidlo, nebo použijte hodnotu jiné než `control_flow_statements`, `expressions`, nebo `type_casts`, nastavení se nepoužije.

Příklady kódu:

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

#### <a name="csharpspacebeforecolonininheritanceclause"></a>csharp\_space\_before\_colon\_in\_inheritance_clause

|||
|-|-|
| **Název pravidla** | csharp_space_before_colon_in_inheritance_clause |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |
| **Hodnoty** | `true` -Vyžadují mezeru před dvojtečku pro základů nebo rozhraní v deklaraci typu<br /><br />`false` -Vyžadují _žádné_ mezeru před dvojtečku pro základů nebo rozhraní v deklaraci typu |
| **Visual Studio default** | `true` |

Příklady kódu:

```csharp
// csharp_space_before_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_before_colon_in_inheritance_clause = false
interface I
{

}

class C: I
{

}
```

#### <a name="csharpspaceaftercolonininheritanceclause"></a>csharp\_space\_after\_colon\_in\_inheritance_clause

|||
|-|-|
| **Název pravidla** | csharp_space_after_colon_in_inheritance_clause |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |
| **Hodnoty** | `true` -Vyžadují mezeru po dvojtečku pro základů nebo rozhraní v deklaraci typu<br /><br />`false` -Vyžadují _žádné_ mezeru po dvojtečku pro základů nebo rozhraní v deklaraci typu |
| **Visual Studio default** | `true` |

Příklady kódu:

```csharp
// csharp_space_after_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_after_colon_in_inheritance_clause = false
interface I
{

}

class C :I
{

}
```

#### <a name="csharpspacearoundbinaryoperators"></a>CSharp\_místo\_kolem\_binary_operators

|||
|-|-|
| **Název pravidla** | csharp_space_around_binary_operators |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |
| **Hodnoty** | `before_and_after` -Vložte mezeru před a za binární operátor<br /><br />`none` -Odeberte mezery před a za binární operátor<br /><br />`ignore` -Ignore mezery kolem binárních operátorů |
| **Visual Studio default** | `before_and_after` |

Pokud můžete vynechat, nechte toto pravidlo, nebo použijte hodnotu jiné než `before_and_after`, `none`, nebo `ignore`, nastavení se nepoužije.

Příklady kódu:

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

#### <a name="csharpspacebetweenmethoddeclarationemptyparameterlistparentheses"></a>csharp_space_between_method_declaration_empty_parameter_list_parentheses

|||
|-|-|
| **Název pravidla** | csharp_space_between_method_declaration_empty_parameter_list_parentheses |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |
| **Hodnoty** | `true` -Vložte mezeru mezi kulaté závorky seznamu prázdný parametr pro deklaraci metody<br /><br />`false` -Odeberte mezeru mezi kulaté závorky seznamu prázdný parametr pro deklaraci metody |
| **Visual Studio default** | `false` |

Příklady kódu:

```csharp
// csharp_space_between_method_declaration_empty_parameter_list_parentheses = true
void Goo( )
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}

// csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharpspacebetweenmethodcallnameandopeningparenthesis"></a>csharp_space_between_method_call_name_and_opening_parenthesis

|||
|-|-|
| **Název pravidla** | csharp_space_between_method_call_name_and_opening_parenthesis |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |
| **Hodnoty** | `true` -Vložte mezeru mezi název metody volání a levou závorku<br /><br />`false` – Odebere mezeru mezi název metody volání a levou závorku |
| **Visual Studio default** | `false` |

Příklady kódu:

```csharp
// csharp_space_between_method_call_name_and_opening_parenthesis = true
void Goo()
{
    Goo (1);
}

void Goo(int x)
{
    Goo ();
}

// csharp_space_between_method_call_name_and_opening_parenthesis = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharpspacebetweenmethodcallemptyparameterlistparentheses"></a>csharp_space_between_method_call_empty_parameter_list_parentheses

|||
|-|-|
| **Název pravidla** | csharp_space_between_method_call_empty_parameter_list_parentheses |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 verze 15.7 |
| **Hodnoty** | `true` -Vložit mezeru mezi kulaté závorky prázdného seznamu argumentů<br /><br />`false` -Odebrat mezeru mezi kulaté závorky prázdného seznamu argumentů |
| **Visual Studio default** | `false` |

Příklady kódu:

```csharp
// csharp_space_between_method_call_empty_parameter_list_parentheses = true
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo( );
}

// csharp_space_between_method_call_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharpspaceaftercomma"></a>csharp_space_after_comma

|||
|-|-|
| **Název pravidla** | csharp_space_after_comma |
| **Použitelné jazyky** | C# |
| **Hodnoty** | `true` -Vkládat mezeru za čárku<br /><br />`false` – Odebere mezeru za čárku |
| **Visual Studio default** | `true` |

Příklady kódu:

```csharp
// csharp_space_after_comma = true
int[] x = new int[] { 1, 2, 3, 4, 5 };

// csharp_space_after_comma = false
int[] x = new int[] { 1,2,3,4,5 }
```

#### <a name="csharpspaceafterdot"></a>csharp_space_after_dot

|||
|-|-|
| **Název pravidla** | csharp_space_after_dot |
| **Použitelné jazyky** | C# |
| **Hodnoty** | `true` -Vkládat mezeru za tečku<br /><br />`false` – Odebere mezeru za tečku |
| **Visual Studio default** | `false` |

Příklady kódu:

```csharp
// csharp_space_after_dot = true
this. Goo();

// csharp_space_after_dot = false
this.Goo();
```

### <a name="wrap-options"></a>Zabalení možnosti

Tato pravidla formátování se týkají používání jednotlivých řádků a samostatné řádky příkazů a bloků kódu.

Příklad *.editorconfig* souboru:

```ini
# CSharp formatting settings:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

#### <a name="csharppreservesinglelinestatements"></a>csharp_preserve_single_line_statements

|||
|-|-|
| **Název pravidla** | csharp_preserve_single_line_statements |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Ponechte příkazy a člen deklarace na stejném řádku<br /><br />`false` -Ponechte příkazy a člen deklarace na samostatné řádky |
| **Visual Studio default** | `true` |

Příklady kódu:

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

#### <a name="csharppreservesinglelineblocks"></a>csharp_preserve_single_line_blocks

|||
|-|-|
| **Název pravidla** | csharp_preserve_single_line_blocks |
| **Použitelné jazyky** | C# |
| **Zavedení verze** | Visual Studio 2017 version 15.3 |
| **Hodnoty** | `true` -Opustit blok kódu na jednom řádku<br /><br />`false` -Opustit blok kódu na samostatných řádcích |
| **Visual Studio default** | `true` |

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

## <a name="see-also"></a>Viz také:

- [Jazykové konvence](editorconfig-language-conventions.md)
- [Zásady vytváření názvů](editorconfig-naming-conventions.md)
- [EditorConfig nastavení konvence psaní kódu .NET](editorconfig-code-style-settings-reference.md)
