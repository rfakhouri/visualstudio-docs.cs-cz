---
title: Přístup k prostředí Visual Studio nebo k jiným hostitelům z textové šablony
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 657abba976e0f0d167651943289296d340981e62
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946514"
---
# <a name="access-visual-studio-or-other-hosts-from-a-text-template"></a>Přístup k sadě Visual Studio nebo k jiným hostitelům z textové šablony

V textové šablony můžete použít metody a vlastnosti, které jsou vystavené hostitele, který provede šablony. Visual Studio je příklad hostitele.

> [!NOTE]
> V šablonách běžný text, ale není v můžete použít hostitele metody a vlastnosti *zpracované* textové šablony.

## <a name="obtain-access-to-the-host"></a>Získat přístup k hostiteli

Chcete-li získat přístup k hostiteli, nastavte `hostspecific="true"` v `template` – direktiva. Nyní můžete pomocí `this.Host`, která má typ <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> Typ má členy, které můžete použít, například vyřešit názvy souborů a protokolu chyb.

### <a name="resolve-file-names"></a>Překlad názvů souborů

Pokud chcete vyhledat úplnou cestu souboru relativně vzhledem k textové šablony, pomocí `this.Host.ResolvePath()`.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.IO" #>
<#
 // Find a path within the same project as the text template:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>
```

### <a name="display-error-messages"></a>Zobrazení chybových zpráv

V tomto příkladu se zaprotokoluje při transformace šablony. Pokud je hostitel Visual Studio, chyby jsou přidány do **seznam chyb**.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.CodeDom.Compiler" #>
<#
  string message = "test message";
  this.Host.LogErrors(new CompilerErrorCollection()
    { new CompilerError(
       this.Host.TemplateFile, // Identify the source of the error.
       0, 0, "0",   // Line, column, error ID.
       message) }); // Message displayed in error window.
#>
```

## <a name="use-the-visual-studio-api"></a>Pomocí sady Visual Studio rozhraní API

Pokud spouštění textové šablony v sadě Visual Studio můžete použít `this.Host` pro přístup ke službě poskytované sadě Visual Studio a všechny balíčky nebo rozšíření, které jsou načteny.

Nastavit hostspecific = "true" a přetypovat `this.Host` k <xref:System.IServiceProvider>.

Tento příklad načte Visual Studio API, <xref:EnvDTE.DTE>, jako služba:

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#
 IServiceProvider serviceProvider = (IServiceProvider)this.Host;
 DTE dte = serviceProvider.GetService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>
```

## <a name="use-hostspecific-with-template-inheritance"></a>HostSpecific pomocí šablony dědičnosti

Zadejte `hostspecific="trueFromBase"` Pokud používáte také `inherits` atributů, a pokud dědí ze šablony, která určuje `hostspecific="true"`. Pokud to neuděláte, může získáte kompilátor upozornění, která vlastnost `Host` bylo deklarováno dvakrát.