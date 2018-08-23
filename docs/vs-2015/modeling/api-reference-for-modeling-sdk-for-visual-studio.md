---
title: Reference k rozhraní API k sadě Modeling SDK pro Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 590c9a69-4e22-4841-bb23-f32e80ec1e76
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 65f8fffbe86bfb80916aa62d3f148795a3c279d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631687"
---
# <a name="api-reference-for-modeling-sdk-for-visual-studio"></a>Referenční dokumentace rozhraní API k sadě Modeling SDK pro sadu Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Reference k rozhraní API pro sada Modeling SDK for Visual Studio](https://docs.microsoft.com/visualstudio/modeling/api-reference-for-modeling-sdk-for-visual-studio).  
  
Visual Studio Visualization and Modeling SDK poskytuje platformu, na kterém jsou vytvořeny nástroje UML a jazyky specifické pro doménu (DSL).  
  
> [!NOTE]
>  Informace o rozhraní API pro modelování UML, naleznete v tématu [Reference k rozhraní API pro rozšíření modelování UML](../modeling/api-reference-for-uml-modeling-extensibility.md). Informace o transformaci textu, naleznete v tématu [přizpůsobení transformace textu T4](../modeling/customizing-t4-text-transformation.md).  
  
 Tato část obsahuje referenční materiál pro obory názvů, které mají názvy, které začínají řetězcem "Microsoft.VisualStudio.Modeling".  
  
|Obor názvů|Obsah|  
|---------------|-------------|  
|<xref:Microsoft.VisualStudio.Modeling?displayProperty=fullName>|Třídy, jako je například ModelElement, což je základní třídou třídy domény, které definujete v DSL.|  
|<xref:Microsoft.VisualStudio.Modeling.Design?displayProperty=fullName>|Třídy, které tvoří část definice DSL.|  
|<xref:Microsoft.VisualStudio.Modeling.Diagnostics?displayProperty=fullName>|Model Store prohlížeč výkonu měření nástroje a.|  
|<xref:Microsoft.VisualStudio.Modeling.Diagrams?displayProperty=fullName>|Třídy, jako je například ShapeElement, což je základní třída všech tvarů, které definujete v DSL.|  
|<xref:Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement?displayProperty=fullName>|Gesta a výběr metody.|  
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition?displayProperty=fullName>|Rozhraní API pro návrháře definici DSL.|  
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.Design?displayProperty=fullName>|Interní třídy návrháře definici DSL.|  
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement?displayProperty=fullName>|Atributy, které vám umožní rozšířit návrháře DSL pomocí příkazů a gest ověření.|  
|<xref:Microsoft.VisualStudio.Modeling.Extensibility?displayProperty=fullName>|Rozšiřující metody pro ModelElement, které implementují rozšíření DSL.|  
|<xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement?displayProperty=fullName>|Atributy rozšíření|  
|<xref:Microsoft.VisualStudio.Modeling.Immutability?displayProperty=fullName>|Umožňuje vytvořit části model jen pro čtení.|  
|<xref:Microsoft.VisualStudio.Modeling.Integration?displayProperty=fullName>|Rozhraní API Modelbus, které vám pomůže integrovat různých modelů.|  
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker?displayProperty=fullName>|Dialogové okno, které mohou uživatelé přejít na modely a prvky k vytvoření odkazů Modelbus.|  
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker.Hosting?displayProperty=fullName>|Výběr služby.|  
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell?displayProperty=fullName>|Modelbus adaptéru rozhraní pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].|  
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell.Picker?displayProperty=fullName>|Dialogové okno Výběr, který mohou uživatelé přejít na modely a prvky k vytvoření odkazů Modelbus.|  
|<xref:Microsoft.VisualStudio.Modeling.Shell?displayProperty=fullName>|Rozhraní mezi DSL a [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].|  
|<xref:Microsoft.VisualStudio.Modeling.Shell.ExtensionEnablement?displayProperty=fullName>|Umožňuje definovat příkazy nabídky zástupců (objektu context).|  
|<xref:Microsoft.VisualStudio.Modeling.Validation?displayProperty=fullName>|Umožňuje definovat omezení ověření.|  
  
## <a name="see-also"></a>Viz také  
 [Reference k rozhraní API pro rozšíření modelování UML](../modeling/api-reference-for-uml-modeling-extensibility.md)   
 [Přizpůsobení transformace textu T4](../modeling/customizing-t4-text-transformation.md)



