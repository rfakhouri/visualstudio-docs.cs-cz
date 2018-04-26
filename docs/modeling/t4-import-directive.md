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
ms.openlocfilehash: 4017ffc67558f6056cb01bf62c5adf9e7569ad4d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
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

- [T4 – direktiva Assembly](../modeling/t4-assembly-directive.md)