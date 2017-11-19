---
title: "Řízení barvu, styl čáry a další vlastnosti tvaru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c06d0066-24aa-4c65-b91c-c2089b81ec8d
caps.latest.revision: "2"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 1d2ed7170189ad48474a7cf8422386b6198ccc9c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
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