---
title: "Postupy: generování šablon ze šablon pomocí řídicích sekvencí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, generating templates from templates
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: "35"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 634d5617d1f42891953f8f1a73bcc5d09a8ffa9b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>Postupy: Generování šablon ze šablon pomocí řídicích sekvencí
Můžete vytvořit šablonu text, který vytváří jinou šablonu text jako výstup generovaný text. K tomuto účelu používaly řídicí sekvence od sebe odděluje textové šablony značky. Pokud nepoužijete řídicí sekvence, bude mít generovaného textové šablony předem definované význam. Další informace o použití řídicích sekvencí v textových šablonách najdete v tématu [pomocí řídicích sekvencí v textových šablonách](../modeling/using-escape-sequences-in-text-templates.md).  
  
### <a name="to-generate-a-text-template-from-within-a-text-template"></a>Ke generování textové šablony z v rámci textové šablony  
  
-   Použít zpětné lomítko (\\) jako řídicí znak vytvářet potřebné značky v rámci šablony text pro direktivy, příkazy, výrazy a třídy funkcí v samostatných textového souboru šablony.  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## <a name="example"></a>Příklad  
 Následující příklad používá k vytvoření šablony text z textové šablony řídicí znaky. `output` – Direktiva nastaví typ cílového souboru do souboru typu text šablony (.tt).  
  
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
  
 Výstup generovaný textu je textové šablony.  
  
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