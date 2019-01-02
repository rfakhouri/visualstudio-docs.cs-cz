---
title: Umístění a velikost obrazce omezení BoundsRules
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 449fb0c12b11163ba0ceca981e66a7da0c399e1c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53950196"
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>Umístění a velikost obrazce omezení BoundsRules

A *hranice pravidlo* je třída, která definuje omezení na velikost a umístění obrazce. Poskytuje metodu, která se nazývá opakovaně, když uživatel přetahuje rohů nebo stranách obrazec nebo obrazce.

Následující příklad omezí tvorbě obdélníkového tvaru bude panel s pevnou velikostí, vodorovný nebo svislý. Když uživatel přetáhne rohů nebo strany, osnovy převrátí mezi dvě konfigurace povolených výšky a šířky.

Rozsah pravidla, je třída odvozena z <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>. V obrazci je vytvořena instance pravidla:

```csharp
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

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>
- [Odpovědi na změny a jejich šíření](../modeling/responding-to-and-propagating-changes.md)