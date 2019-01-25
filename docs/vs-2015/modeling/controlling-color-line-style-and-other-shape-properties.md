---
title: Řízení barvy, stylu čáry a ostatních vlastností obrazce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: c06d0066-24aa-4c65-b91c-c2089b81ec8d
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cff60ca7fc76563db73c4fc839688e0fba4ab975
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54785991"
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>Řízení barvy, stylu čáry a ostatních vlastností obrazce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Některé vlastnosti obrazce, jako je barva by bylo možné "vystavit" – to znamená, propojené na doménovou vlastnost obrazce. Ostatní uživatelé mají přímo se dá řídit.  
  
## <a name="exposing-a-property"></a>Vystavení vlastností  
 Některé vlastnosti obrazce, jako je barva může být propojený hodnoty vlastnosti domény.  
  
 V definici DSL vyberte obrazec, konektoru nebo diagramu třídy. V kontextové nabídce, zvolte **přidat vystavený**a klikněte na tlačítko Vlastnosti, třeba Barva výplně.  
  
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
