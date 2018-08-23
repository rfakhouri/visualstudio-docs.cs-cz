---
title: T4 Import – direktiva | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 713ca975-b9aa-4210-bf6d-b7660f5b193b
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 2b0b4332f9c156bc9690ef94f8670e963203b5a9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666983"
---
# <a name="t4-import-directive"></a>T4 – direktiva Import
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [T4 – Direktiva Import](https://docs.microsoft.com/visualstudio/modeling/t4-import-directive).  
  
V blocích kódu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] textové šablony T4 `import` – direktiva umožňuje odkazovat na prvky v jiném oboru názvů bez zadání plně kvalifikovaný název. Je ekvivalentem `using` v jazyce C# nebo `imports` v [!INCLUDE[vb_current_short](../includes/vb-current-short-md.md)].  
  
 Obecný přehled o psaní textových šablon T4 naleznete v tématu [vytvoření textové šablony T4](../modeling/writing-a-t4-text-template.md).  
  
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
  
-   Obor názvů vašeho kódu DSL  
  
## <a name="see-also"></a>Viz také  
 [T4 – direktiva Assembly](../modeling/t4-assembly-directive.md)



