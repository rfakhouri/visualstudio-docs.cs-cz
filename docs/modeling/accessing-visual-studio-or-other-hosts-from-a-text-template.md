---
title: "Přístup k sadě Visual Studio nebo k jiným hostitelům z textové šablony | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: cd72a2838e9dd7a903e5cf76aac30e2922708872
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>Přístup k prostředí Visual Studio nebo k jiným hostitelům z textové šablony
V textové šablony, můžete použít metody a vlastnosti, které jsou vystavené hostitele, který provede šablony, jako například [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 To platí pro běžný text šablony, není předběžně zpracované textové šablony.  
  
## <a name="obtaining-access-to-the-host"></a>Získání přístupu k hostiteli  
 Nastavit `hostspecific="true"` v `template` – direktiva. To vám umožní využívat `this.Host`, která má typ <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Tento typ má členy, které můžete použít, například přeložit názvy souborů a chyb do protokolu.  
  
### <a name="resolving-file-names"></a>Řešení názvů souborů  
 Úplná cesta souboru relativně vzhledem k textové šablony najdete použijte. Host.ResolvePath().  
  
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
 V tomto příkladu se zaprotokoluje při transformace šablony. Pokud je hostitel [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], přidají se do okna chyby.  
  
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
  
## <a name="using-the-visual-studio-api"></a>Pomocí sady Visual Studio rozhraní API  
 Pokud jsou prováděny textové šablony v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], můžete použít `this.Host` pro přístup ke službě poskytované [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a všechny balíčky nebo rozšíření, které jsou načteny.  
  
 Nastavit hostspecific = "true" a přetypovat `this.Host` k <xref:System.IServiceProvider>.  
  
 Tento příklad načte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozhraní API, <xref:EnvDTE.DTE>, jako služba:  
  
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
  
## <a name="using-hostspecific-with-template-inheritance"></a>HostSpecific pomocí šablony dědičnosti  
 Zadejte `hostspecific="trueFromBase"` Pokud používáte také `inherits` atributů, a pokud dědí ze šablony, která určuje `hostspecific="true"`. Tím je zabráněno upozornění kompilátoru o tom, který vlastnost `Host` bylo deklarováno dvakrát.