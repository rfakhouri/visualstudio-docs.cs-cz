---
title: Řízení barvu, styl čáry a další vlastnosti tvaru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: e49e6cbc6ecfba85e2c2684b0a7e71e05757ab59
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>Řízení barvy, stylu čáry a ostatních vlastností obrazce
Některé vlastnosti tvaru, jako je barva mohou být 'zpřístupněny' – to znamená, propojit vlastnost domain tvaru. Ostatní uživatelé mají pro řízení přímo.  
  
## <a name="exposing-a-property"></a>Vystavení vlastností  
 Některé vlastnosti tvaru například barva lze propojit s hodnotou vlastnosti domény.  
  
 V definici DSL vyberte tvaru, konektoru nebo diagram třídy. V místní nabídce, zvolte **přidat zveřejněné**a potom vyberte vlastnost má, jako je například barva výplně.  
  
 Tvar, který má nyní vlastnosti domény, která můžete nastavit v programovém kódu nebo jako uživatel.  
  
## <a name="dynamically-updating-an-exposed-property"></a>Dynamicky aktualizuje zveřejněné vlastnost  
 Obvykle má být vlastnost zveřejněné závisí na jiné vlastnosti. Můžete například obrazce na červenou barvu vždy, když je vlastnost konkrétní domény menší než nula. Chcete-li tuto závislost, vytvořte [pravidlo](../modeling/rules-propagate-changes-within-the-model.md). Příklad:  
  
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