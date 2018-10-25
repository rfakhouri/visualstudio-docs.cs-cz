---
title: Referenční dokumentace rozhraní API k sadě Modeling SDK pro sadu Visual Studio
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 21da4ff34c26d28944af5edcb14e40b2db0d94d7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49896963"
---
# <a name="api-reference-for-modeling-sdk-for-visual-studio"></a>Referenční dokumentace rozhraní API k sadě Modeling SDK pro sadu Visual Studio

Visual Studio Visualization and Modeling SDK poskytuje platformu, na kterém jsou integrované nástroje pro jazyky specifické pro doménu (DSL).

Tato část obsahuje referenční materiál pro obory názvů, které mají názvy, které začínají řetězcem "Microsoft.VisualStudio.Modeling".

|Obor názvů|Obsah|
|-|-|
|<xref:Microsoft.VisualStudio.Modeling?displayProperty=fullName>|Třídy, jako je například ModelElement, což je základní třídou třídy domény, které definujete v DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Design?displayProperty=fullName>|Třídy, které tvoří část definice DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Diagnostics?displayProperty=fullName>|Model Store prohlížeč výkonu měření nástroje a.|
|<xref:Microsoft.VisualStudio.Modeling.Diagrams?displayProperty=fullName>|Třídy, jako je například ShapeElement, což je základní třída všech tvarů, které definujete v DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement?displayProperty=fullName>|Gesta a výběr metody.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition?displayProperty=fullName>|Rozhraní API pro návrháře definici DSL.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.Design?displayProperty=fullName>|Interní třídy návrháře definici DSL.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement?displayProperty=fullName>|Atributy, které vám umožní rozšířit Návrhář DSL s příkazy, gesta a ověřování.|
|<xref:Microsoft.VisualStudio.Modeling.Extensibility?displayProperty=fullName>|Rozšiřující metody pro ModelElement, které implementují rozšíření DSL.|
|<xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement?displayProperty=fullName>|Atributy rozšíření|
|<xref:Microsoft.VisualStudio.Modeling.Immutability?displayProperty=fullName>|Umožňuje vytvořit části model jen pro čtení.|
|<xref:Microsoft.VisualStudio.Modeling.Integration?displayProperty=fullName>|Rozhraní API Modelbus, které vám pomůže integrovat různých modelů.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker?displayProperty=fullName>|Dialogové okno, které mohou uživatelé přejít na modely a prvky k vytvoření odkazů Modelbus.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker.Hosting?displayProperty=fullName>|Výběr služby.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell?displayProperty=fullName>|Modelbus adaptéru rozhraní pro sadu Visual Studio.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell.Picker?displayProperty=fullName>|Dialogové okno Výběr, který mohou uživatelé přejít na modely a prvky k vytvoření odkazů Modelbus.|
|<xref:Microsoft.VisualStudio.Modeling.Shell?displayProperty=fullName>|Rozhraní mezi DSL a sady Visual Studio.|
|<xref:Microsoft.VisualStudio.Modeling.Shell.ExtensionEnablement?displayProperty=fullName>|Umožňuje definovat příkazy nabídky zástupců (objektu context).|
|<xref:Microsoft.VisualStudio.Modeling.Validation?displayProperty=fullName>|Umožňuje definovat omezení ověření.|

## <a name="see-also"></a>Viz také

- [Přizpůsobení transformace textu T4](../modeling/customizing-t4-text-transformation.md)
