---
title: "Řízení barvu, styl čáry a další vlastnosti tvaru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5903c6cc79e637514b75c9e44cb4cbe5c0342ee7
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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