---
title: "T4 Import – direktiva | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f9d3abdc07b2fc937b08431df4d7d4e75800e700
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="t4-import-directive"></a>T4 – direktiva Import
V blocích kódu po [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] textové šablony T4 `import` – direktiva umožňuje odkazovat na elementy v jiném oboru názvů bez zadání plně kvalifikovaný název. Je ekvivalentem `using` v jazyce C# nebo `imports` v [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)].  
  
 Obecné přehled tvorbu textových šablon T4, najdete v tématu [zápis textové šablony T4](../modeling/writing-a-t4-text-template.md).  
  
## <a name="using-the-import-directive"></a>Použití direktivy importu  
  
```  
<#@ import namespace="namespace" #>  
```  
  
 V tomto příkladu se v kódu šablony může vynechat explicitní obor názvů pro členy System.IO:  
  
```  
<#@ import namespace="System.IO" #>  
<#   
   string fileContent = File.ReadAllText("C:\x.txt"); // System.IO.File  
#>   
The file contains: <#=  fileContent #>  
```  
  
## <a name="standard-imports"></a>Standardní importy  
 Následující obor názvů se importuje automaticky, takže pro něj není nutné psát direktivu importu:  
  
-   `System`  
  
 Pokud použijete vlastní direktivu, může navíc procesor direktiv importovat některé obory názvů automaticky.  
  
 Pokud například píšete šablony pro jazyk domény (DSL), nemusíte psát direktivy importu pro následující obory názvů:  
  
-   `Microsoft.VisualStudio.Modeling`  
  
-   Obor názvů vaší DSL  
  
## <a name="see-also"></a>Viz také  
 [T4 – direktiva Assembly](../modeling/t4-assembly-directive.md)