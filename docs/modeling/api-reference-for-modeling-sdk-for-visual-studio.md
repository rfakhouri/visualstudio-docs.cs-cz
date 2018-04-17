---
title: Referenční dokumentace rozhraní API pro modelování SDK pro Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: e8b1b913a925877715d8fa603df5ad9e3a4ff175
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="api-reference-for-modeling-sdk-for-visual-studio"></a>Referenční dokumentace rozhraní API k sadě Modeling SDK pro sadu Visual Studio
Visual Studio vizualizace a modelování SDK poskytuje platformu, na kterém jsou vytvořeny vaší nástroje specifické pro doménu jazyky (DSL).  
  
 Tato část obsahuje referenčního materiálu pro obory názvů, které mají názvy, které začínají "Microsoft.VisualStudio.Modeling".  
  
|Obor názvů|Obsah|  
|---------------|-------------|  
|<xref:Microsoft.VisualStudio.Modeling?displayProperty=fullName>|Třídy, jako je ModelElement, která je základní třídou třídy domény, které definujete v DSL.|  
|<xref:Microsoft.VisualStudio.Modeling.Design?displayProperty=fullName>|Třídy, které tvoří součást DSL definice.|  
|<xref:Microsoft.VisualStudio.Modeling.Diagnostics?displayProperty=fullName>|Model prohlížeč úložiště a výkon nástroje měření.|  
|<xref:Microsoft.VisualStudio.Modeling.Diagrams?displayProperty=fullName>|Třídy, jako je ShapeElement, která je základní třída všech tvarů, které definujete v DSL.|  
|<xref:Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement?displayProperty=fullName>|Gesto a výběr metody.|  
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition?displayProperty=fullName>|Rozhraní API Návrháře DSL definice.|  
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.Design?displayProperty=fullName>|Interní třídy návrháře DSL definice.|  
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement?displayProperty=fullName>|Atributy, které umožňují rozšířit návrháře DSL s příkazy, gesta a ověření.|  
|<xref:Microsoft.VisualStudio.Modeling.Extensibility?displayProperty=fullName>|Rozšiřující metody pro ModelElement které implementují DSL rozšíření.|  
|<xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement?displayProperty=fullName>|Rozšiřitelnost atributy|  
|<xref:Microsoft.VisualStudio.Modeling.Immutability?displayProperty=fullName>|Umožňuje provádět částí modelu jen pro čtení.|  
|<xref:Microsoft.VisualStudio.Modeling.Integration?displayProperty=fullName>|Rozhraní API Modelbus, které vám umožní integrovat různé modely.|  
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker?displayProperty=fullName>|Dialogové okno, která umožňuje uživatelům, přejděte na modely a elementy, aby mohla vytvořit odkazy Modelbus.|  
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker.Hosting?displayProperty=fullName>|Výběr služby.|  
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell?displayProperty=fullName>|Modelbus adaptéru rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell.Picker?displayProperty=fullName>|Dialogové okno Výběr, která umožňuje uživatelům, přejděte na modely a elementy, aby mohla vytvořit odkazy Modelbus.|  
|<xref:Microsoft.VisualStudio.Modeling.Shell?displayProperty=fullName>|Rozhraní mezi DSL, linky a [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|<xref:Microsoft.VisualStudio.Modeling.Shell.ExtensionEnablement?displayProperty=fullName>|Umožňuje definovat příkazy nabídky zástupce (kontextu).|  
|<xref:Microsoft.VisualStudio.Modeling.Validation?displayProperty=fullName>|Umožňuje definovat omezení ověřování.|  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení transformace textu T4](../modeling/customizing-t4-text-transformation.md)
