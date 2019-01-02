---
title: 'Postupy: Generování šablon ze šablon pomocí řídicích sekvencí'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, generating templates from templates
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 8aa0d2203db6080260bc702429758fbd7f6b1a4a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53938144"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>Postupy: Generování šablon ze šablon pomocí řídicích sekvencí
Můžete vytvořit textové šablony, která vytvoří jiné textové šablony jako jeho vygenerovaný textový výstup. Chcete-li to provést, musíte použít řídicí sekvence od sebe odděluje textové šablony značky. Pokud nepoužijete řídicí sekvence, generované textové šablony se mají předem definované význam. Další informace o použití řídicích sekvencí v textových šablonách naleznete v tématu [pomocí řídicích sekvencí v textových šablonách](../modeling/using-escape-sequences-in-text-templates.md).

### <a name="to-generate-a-text-template-from-within-a-text-template"></a>Ke generování textové šablony z v rámci textové šablony

-   Použít zpětné lomítko (\\) jako řídicí znak vytvářel potřebné značky v rámci textové šablony pro direktivy, příkazy, výrazy a funkce v samostatném textovém souboru šablony třídy.

    ```
    \<#@ directive \#>
    \<# statement \#>
    \<#= expression \#>
    \<#+ classfeature \#>
    ```

## <a name="example"></a>Příklad
 Následující příklad používá řídicí znaky pro vytvoření textové šablony z textové šablony. `output` – Direktiva nastaví cílový typ souboru pro typ souboru textové šablony (.tt).

```csharp
\<#@ output extension=".tt" \#>
\<#@ assembly name="System.Xml.dll" \#>
\<#@ import namespace="System.Xml" \#>
\<#
XmlDocument xDoc = new XmlDocument();
//System.Diagnostics.Debugger.Break();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {\#>
           \<#= attr.Name \#>
       \<#}
     }
\#>
```

 Vygenerovaný textový výstup je textové šablony.

```
<#@ output extension=".tt" #>
<#@ assembly name="System.Xml.dll" #>
<#@ import namespace="System.Xml" #>
<#
XmlDocument xDoc = new XmlDocument();
//System.Diagnostics.Debugger.Break();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {#>
           <#= attr.Name #>
       <#}
     }
#>
```