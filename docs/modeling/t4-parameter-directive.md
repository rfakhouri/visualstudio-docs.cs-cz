---
title: T4 – direktiva Parameter
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 1f12363af0d0b26aa72c5478df5da82c6d4fd02a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="t4-parameter-directive"></a>T4 – direktiva Parameter

V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] textové šablony `parameter` ohlašuje vlastnosti ve vašem kódu šablony, které jsou inicializovány z hodnoty předané z externí kontextu. Tyto hodnoty můžete nastavit, pokud napsat kód, který vyvolá transformace textu.

## <a name="using-the-parameter-directive"></a>Pomocí parametru – direktiva

```
<#@ parameter type="Full.TypeName" name="ParameterName" #>
```

 `parameter` Ohlašuje vlastnosti ve vašem kódu šablony, které jsou inicializovány z hodnoty předané z externí kontextu. Tyto hodnoty můžete nastavit, pokud napsat kód, který vyvolá transformace textu. Mohou být předány hodnoty, buď v `Session` slovník, nebo v <xref:System.Runtime.Remoting.Messaging.CallContext>.

 Je možné deklarovat parametry libovolného typu učinit vzdáleným. To znamená typ musí být deklarována s <xref:System.SerializableAttribute>, nebo musí být odvozeny od <xref:System.MarshalByRefObject>. To umožňuje hodnoty parametrů, které mají být předány do domény aplikace, ve kterém je šablonu zpracovat.

 Můžete například napsat textové šablony s následujícím obsahem:

```
<#@ template language="C#" #>

<#@ parameter type="System.Int32" name="TimesToRepeat" #>

<# for (int i = 0; i < TimesToRepeat; i++) { #>
Line <#= i #>
<# } #>

```

## <a name="passing-parameter-values-to-a-template"></a>Předávání hodnot parametrů šablony
 Pokud píšete [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření například příkazu nabídky nebo obslužné rutiny události při zpracování šablony pomocí služby ukázka text:

```csharp
// Get a service provider - how you do this depends on the context:
IServiceProvider serviceProvider = dte; // or dslDiagram.Store, for example
// Get the text template service:
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;
// Create a Session in which to pass parameters:
host.Session = host.CreateSession();
// Add parameter values to the Session:
session["TimesToRepeat"] = 5;
// Process a text template:
string result = t4.ProcessTemplate("MyTemplateFile.t4",
  System.IO.File.ReadAllText("MyTemplateFile.t4"));

```

## <a name="passing-values-in-the-call-context"></a>Předávání hodnot v kontextu volání
 Můžete případně předat hodnoty jako logické data v <xref:System.Runtime.Remoting.Messaging.CallContext>.

 Následující příklad předá hodnoty pomocí obou metod:

```csharp
ITextTemplating t4 = this.Store.GetService(typeof(STextTemplating)) as ITextTemplating;
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;
host.Session = host.CreateSession();
// Pass a value in Session:
host.Session["p1"] = 32;
// Pass another value in CallContext:
System.Runtime.Remoting.Messaging.CallContext.LogicalSetData("p2", "test");

// Process a small template inline:
string result = t4.ProcessTemplate("",
   "<#@parameter type=\"System.Int32\" name=\"p1\"#>"
 + "<#@parameter type=\"System.String\" name=\"p2\"#>"
 + "Test <#=p1#> <#=p2#>");

// Result value is:
//     Test 32 test

```

## <a name="passing-values-to-a-run-time-preprocessed-text-template"></a>Předávání hodnot Run-Time (Preprocessed) textové šablony
 Není obvykle nutné k použití `<#@parameter#>` direktivy s runtime (předběžně zpracované) textové šablony. Místo toho můžete definovat další konstruktoru nebo nastavit vlastnost pro generovaný kód, pomocí kterého můžete předat hodnoty parametrů. Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).

 Ale pokud budete chtít použít `<#@parameter>` v šabloně běhu, můžete předat hodnoty do ho pomocí slovníku relace. Jako příklad předpokládejme, že jste vytvořili jako šablonu předběžně zpracované názvem souboru `PreTextTemplate1`. Pomocí následujícího kódu můžete vyvolat šablony v programu.

```csharp
PreTextTemplate1 t = new PreTextTemplate1();
t.Session = new Microsoft.VisualStudio.TextTemplating.TextTemplatingSession();
t.Session["TimesToRepeat"] = 5;
// Add other parameter values to t.Session here.
t.Initialize(); // Must call this to transfer values.
string resultText = t.TransformText();

```

## <a name="obtaining-arguments-from-texttemplateexe"></a>Získání argumenty z TextTemplate.exe

> [!IMPORTANT]
>  `parameter` – Direktiva nenačítá hodnotami nastavenými `-a` parametr `TextTransform.exe` nástroj. Chcete-li získat tyto hodnoty, nastavte `hostSpecific="true"` v `template` směrnice a použití `this.Host.ResolveParameterValue("","","argName")`.