---
title: T4 – direktiva Import
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: c14cfea94277158583717aa77edc4636f245e58a
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/01/2018
ms.locfileid: "47857851"
---
# <a name="t4-import-directive"></a>T4 – direktiva Import

V blocích kódu textové šablony Visual Studio T4 `import` – direktiva umožňuje odkazovat na prvky v jiném oboru názvů bez zadání plně kvalifikovaného názvu. Je ekvivalentem `using` v jazyce C# nebo `imports` v [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)].

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

- [T4 – direktiva Assembly](../modeling/t4-assembly-directive.md)