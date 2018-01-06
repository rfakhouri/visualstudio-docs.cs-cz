---
title: "BoundsRules omezit tvar umístění a velikost | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, events
ms.assetid: 4d08e541-fc67-4e68-bf31-30d346aa2aa0
caps.latest.revision: "18"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 81c6ab1f043074b4da601dbfe2d3dc52243b00e5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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