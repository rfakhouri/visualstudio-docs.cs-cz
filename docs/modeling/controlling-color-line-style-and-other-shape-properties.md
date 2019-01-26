---
title: Řízení barvy, stylu čáry a ostatních vlastností obrazce
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: e9ff795195381b9b514f96487d30167b061be429
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55026165"
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>Řízení barvy, stylu čáry a ostatních vlastností obrazce

Některé vlastnosti obrazce, jako je barva můžou "zveřejnit". To znamená vlastnosti lze propojit na doménovou vlastnost obrazce. Ostatní uživatelé mají přímo se dá řídit.

## <a name="exposing-a-property"></a>Vystavení vlastností
 Některé vlastnosti obrazce, jako je barva může být propojený hodnoty vlastnosti domény.

 V definici DSL vyberte obrazec, konektoru nebo diagramu třídy. V místní nabídce, zvolte **přidat vystavený**a klikněte na tlačítko Vlastnosti, třeba Barva výplně.

 Doménová vlastnost, kterou můžete nastavit v kódu programu nebo jako uživatel nyní má obrazec.

## <a name="dynamically-updating-an-exposed-property"></a>Dynamické aktualizace vystavené vlastnosti
 Obvykle nechcete se ujistit vlastnost vystavené závisí na jiné vlastnosti. Můžete například obrazec, který chcete červenou pokaždé, když se konkrétní doménová vlastnost, která je menší než nula. Pokud chcete nastavit tuto závislost, vytvořit [pravidlo](../modeling/rules-propagate-changes-within-the-model.md). Příklad:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;
namespace ExampleNamespace
{
 // Attribute associates the rule with class:
 [RuleOn(typeof(CarShape), FireTime = TimeToFire.TopLevelCommit)]
 // The rule is a class derived from one of the abstract rules:
 class CarShapeAddRule : AddRule
 {
 // Override the abstract method:
 public override void ElementAdded(ElementAddedEventArgs e)
 {
 base.ElementAdded(e);
 CarShape shape = e.ModelElement as CarShape;
 Store store = shape.Store;
 // Ignore this call if we're currently loading a model:
 if (store.TransactionManager.CurrentTransaction.IsSerializing)
  return;
 Car car = shape.ModelElement as Car;
 // Code here propagates change as required - for example:
 shape.FillColor = car.Somebool ? System.Drawing.Color.Red : System.Drawing.Color.Green;
 }
}
 // The rule must be registered:
 public partial class ExampleDomainModel
 {
 protected override Type[] GetCustomDomainModelTypes()
 {
  List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());
  types.Add(typeof(CarShapeAddRule));
  // If you add more rules, list them here.
  return types.ToArray();
 }
 }
}
```