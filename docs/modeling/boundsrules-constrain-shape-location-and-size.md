---
title: BoundsRules omezit tvar umístění a velikost | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2474040edc439aad8a9dd75826d4918e6773e186
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>Umístění a velikost obrazce omezení BoundsRules
A *hranice pravidlo* je třída, která definuje omezení na velikost a umístění obrazce. Poskytuje metodu, která je volána opakovaně, když uživatel je přetáhnete obrazce nebo rozích nebo stranách obrazce.  
  
 Následující příklad omezí pravoúhlému tvaru jako panel s pevnou velikostí, vodorovně nebo svisle. Když uživatel nastavuje tažením rozích nebo stranách, obrys převrátí mezi dvě konfigurace povolených výšky a šířky.  
  
 Rozsah pravidla je třída odvozená z <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>. Instance pravidla je vytvořen ve tvaru:  
  
```  
using Microsoft.VisualStudio.Modeling.Diagrams; ...  
public partial class BarShape  
{  
  /// <summary>  
  /// Rule invoked when the user is resizing a shape.  
  /// </summary>  
  public override BoundsRules BoundsRules  
  { get { return new BarBoundsRule(); } }  
}  
/// <summary>  
/// Rule invoked when the user is changing a shape's outline.  
/// Provides real-time mouse rubber-band feedback, so must work fast.  
/// </summary>  
public class BarBoundsRule: BoundsRules  
{   
  public override RectangleD GetCompliantBounds   
     (ShapeElement shape, RectangleD proposedBounds)  
  {  
    double thickness = 0.1;  
    if (proposedBounds.Height > proposedBounds.Width)  
    {  
      // There is a minimum width for a shape; the width  
      // will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
            new SizeD(thickness, proposedBounds.Height));  
    }  
    else  
    {  
      // There is a minimum height for a shape; the   
      // height will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
         new SizeD(proposedBounds.Width, thickness));  
} } }  
```  
  
 Všimněte si, že umístění a velikost můžete omezené, pokud chcete.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>   
 [Reagování na změny a šíření změn](../modeling/responding-to-and-propagating-changes.md)