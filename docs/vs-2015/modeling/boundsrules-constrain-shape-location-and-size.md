---
title: Umístění a velikost obrazce omezení BoundsRules | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, events
ms.assetid: 4d08e541-fc67-4e68-bf31-30d346aa2aa0
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: cafcf44bc1365b74474b201a01d0089465cc7430
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670147"
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>Umístění a velikost obrazce omezení BoundsRules
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [BoundsRules omezení umístění a velikost obrazce](https://docs.microsoft.com/visualstudio/modeling/boundsrules-constrain-shape-location-and-size).  
  
A *hranice pravidlo* je třída, která definuje omezení na velikost a umístění obrazce. Poskytuje metodu, která se nazývá opakovaně, když uživatel přetahuje rohů nebo stranách obrazec nebo obrazce.  
  
 Následující příklad omezí tvorbě obdélníkového tvaru bude panel s pevnou velikostí, vodorovný nebo svislý. Když uživatel přetáhne rohů nebo strany, osnovy převrátí mezi dvě konfigurace povolených výšky a šířky.  
  
 Rozsah pravidla, je třída odvozena z <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>. V obrazci je vytvořena instance pravidla:  
  
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
  
 Všimněte si, že umístění a velikost může být omezena potřebujete.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>   
 [Reagování na změny a šíření změn](../modeling/responding-to-and-propagating-changes.md)



