---
title: Přístup k sadě Visual Studio 2015 nebo k jiným hostitelům z textové šablony | Dokumentace Microsoftu
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: a68886da-7416-4785-8145-3796bb382cba
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d26c168780051d3644d04d209001bf0cc9a551cb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179085"
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>Přístup k prostředí Visual Studio nebo k jiným hostitelům z textové šablony
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V textové šabloně, můžete použít metody a vlastnosti hostitele, který se spustí šablony, jako například [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].

 To platí pro pravidelné textových šablon, ne Předzpracované textové šablony.

## <a name="obtaining-access-to-the-host"></a>Získání přístupu k hostiteli
 Nastavte `hostspecific="true"` v `template` směrnice. To vám umožní používat `this.Host`, která má typ <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Tento typ obsahuje členy, které používáte, třeba k překladu názvů souborů a k protokolování chyb.

### <a name="resolving-file-names"></a>Řešení názvů souborů
 Pokud chcete najít úplnou cestu k souboru relativně vzhledem k textu šablony, použijte. Host.ResolvePath().

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

### <a name="displaying-error-messages"></a>Zobrazení chybových zpráv
 V tomto příkladu se zaprotokoluje při transformaci šablony. Pokud je hostitel [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], přidají se do okna chyby.

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

## <a name="using-the-visual-studio-api"></a>Použití rozhraní API sady Visual Studio
 Pokud jsou spuštěny v textové šabloně [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], můžete použít `this.Host` pro přístup ke službám poskytuje [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a balíčky nebo rozšíření, která jsou načtena.

 Nastavit hostspecific = "true" a přetypovat `this.Host` k <xref:System.IServiceProvider>.

 Tento příklad načte [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozhraní API, <xref:EnvDTE.DTE>, jako služba:

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

## <a name="using-hostspecific-with-template-inheritance"></a>Pomocí šablony dědičnosti hostSpecific
 Zadejte `hostspecific="trueFromBase"` Pokud používáte také `inherits` atribut, a pokud je zděděn ze šablony, která určuje `hostspecific="true"`. Tím se vyhnete upozornění kompilátoru o tom, která vlastnost `Host` byla deklarována dvakrát.
