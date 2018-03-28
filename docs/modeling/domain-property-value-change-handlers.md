---
title: Domény vlastnost hodnota obslužné rutiny změny v sadě Visual Studio | Microsoft Docs
ms.date: 03/22/2018
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, overriding event handlers
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: c806ed3b93bc79e2ea732905b2ff5c7827e43e6a
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="domain-property-value-change-handlers"></a>Domény vlastnost hodnota změnu obslužné rutiny

V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] jazyka domény, při změně hodnoty vlastnosti domény, `OnValueChanging()` a `OnValueChanged()` metody jsou vyvolány v obslužné rutině vlastnost domény. Reagovat na změny, můžete přepsat tyto metody.

## <a name="override-the-property-handler-methods"></a>Přepsání metody vlastnost obslužné rutiny

Každou vlastnost domény jazyka specifické pro doménu používá třídu, která je vnořit do své nadřazené třídy domény. Následuje její název ve formátu *PropertyName*PropertyHandler. Tato vlastnost obslužná rutina třída v souboru si můžete prohlédnout **Dsl\Generated Code\DomainClasses.cs**. Ve třídě `OnValueChanging()` je volána bezprostředně před provedením změny hodnot a `OnValueChanged()` je volána hned po změně hodnoty.

Předpokládejme například, máte domény třídy s názvem `Comment` má vlastnost domény řetězec s názvem `Text` a ve vlastnosti integer s názvem `TextLengthCount`. Způsobí `TextLengthCount` vždy tak, aby obsahovala délka `Text` řetězec, můžete napsat následující kód do samostatného souboru v projektu Dsl:

```csharp
// Domain Class "Comment":
public partial class Comment
{
  // Domain Property "Text":
  partial class TextPropertyHandler
  {
    protected override void OnValueChanging(CommentBase element, string oldValue, string newValue)
    {
      base.OnValueChanging(element, oldValue, newValue);

      // To update values outside the Store, write code here.

      // Let the transaction manager handle undo:
      Store store = element.Store;
      if (store.InUndoRedoOrRollback || store.InSerializationTransaction) return;

      // Update values in the Store:
      this.TextLengthCount = newValue.Length;
    }
  }
}
```

Všimněte si následujících bodů o vlastnost obslužné rutiny:

-   Když uživatel provede změny pro vlastnost domain, i když kód programu přiřadí jinou hodnotu pro vlastnost volání těchto metod vlastnost obslužné rutiny.

-   Pouze při změně hodnoty ve skutečnosti volání těchto metod. Obslužná rutina není vyvolána, pokud kód programu přiřadí hodnotu, která je stejná jako aktuální hodnota.

-   Vlastnosti úložiště počítaný a vlastní domény nemají OnValueChanged a OnValueChanging metody.

-   Obslužná rutina změny nelze použít k úpravě novou hodnotu. Pokud chcete udělat, například k omezení hodnoty na konkrétní rozsah, definování `ChangeRule`.

-   Nelze přidat obslužnou rutinu změn vlastnosti, která představuje roli relace. Místo toho definujte `AddRule` a `DeleteRule` na třídu vztahu. Tato pravidla se aktivuje, když odkazy jsou vytvořené nebo změněné. Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).

### <a name="changes-in-and-out-of-the-store"></a>Změny a deaktivovat úložiště

Vlastnost obslužná rutina metody jsou volány v transakci, která iniciovala změnu. Proto můžete provést další změny v úložišti bez otevření novou transakci. Změny může mít za následek další obslužnou rutinu volání.

Když se vrací zpět transakci, znovu, nebo vrácena zpět, neprovádějte změny v úložišti, to znamená, změní elementů modelu, vztahů, tvarů, konektory diagramy nebo jejich vlastnosti.

Kromě toho by obvykle aktualizujete hodnoty při načítání modelu ze souboru.

Změny modelu by měl být chráněn proto testem takto:

```csharp
if (!store.InUndoRedoOrRollback && !store. InSerializationTransaction)
{
   this.TextLength = ...; // in-store changes
}
```

Naopak pokud vaší obslužné rutiny vlastnost šíří změny mimo úložiště, například na soubor, databázi nebo proměnné bez úložiště, pak můžete by měla vždy provést tyto změny, aby externí hodnoty jsou aktualizovány při vrácení zpět vyvolá uživatele nebo znovu provést.

### <a name="cancel-a-change"></a>Zrušit změnu

Pokud chcete, aby se zabránilo změně, je aktuální transakci vrátit zpět. Například můžete chtít zajistit, aby vlastnost zůstal do určitého rozsahu.

```csharp
if (newValue > 10)
{
   store.TransactionManager.CurrentTransaction.Rollback();
   System.Windows.Forms.MessageBox.Show("Value must be less than 10");
}
```

### <a name="alternative-technique-calculated-properties"></a>Alternativní postup: vypočítat vlastnosti

Předchozí příklad ukazuje, jak lze pomocí OnValueChanged() šíření hodnoty z vlastnosti jedné domény na jiný. Každá vlastnost má svou vlastní uložené hodnoty.

Místo toho zvažte definování odvozená vlastnost jako vlastnost vypočítaná. V tom případě vlastnost nemá žádný úložiště a je definování funkce vyhodnotí se vždy, když její hodnota je povinná. Další informace najdete v tématu [vypočítaná a vlastní vlastnosti úložiště](../modeling/calculated-and-custom-storage-properties.md).

Místo na předchozí příklad, můžete nastavit **druhu** pole z `TextLengthCount` být **vypočítaná** v definici DSL. By poskytnout vlastní **získat** metoda pro tuto vlastnost domény. **Získat** metoda vrátí aktuální délka `Text` řetězec.

Potenciální nevýhodou počítané vlastnosti je ale, že je tento výraz vyhodnocen pokaždé, když bude použita hodnota, které mohou představovat problémy s výkonem. Navíc není žádná OnValueChanging() a OnValueChanged() u počítané vlastnosti.

### <a name="alternative-technique-change-rules"></a>Alternativní postup: změnit pravidla

Pokud definujete ChangeRule, se spustí na konci transakce, ve kterém se změny vlastnosti na hodnotu.  Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).

Pokud v jedné transakci několik změn, ChangeRule provede, když jsou všechny dokončené. Naopak OnValue... metody se spustí, až se některé změny nebyly provedeny. V závislosti na tom, co chcete dosáhnout proto může být ChangeRule vhodnější.

Můžete také ChangeRule upravit novou hodnotu vlastnosti, aby do určitého rozsahu.

> [!WARNING]
> Pokud pravidlo provede změny v úložišti obsahu, může aktivuje další pravidla a vlastnost obslužné rutiny. Pokud se pravidlo změní vlastnost, která se spustí, bude volán znovu. Musí se ujistěte, že pravidlo definic nezpůsobovalo neustálé nekonečná aktivován.

```csharp
using Microsoft.VisualStudio.Modeling;
...
// Change rule on the domain class Comment:
[RuleOn(typeof(Comment), FireTime = TimeToFire.TopLevelCommit)]
class MyCommentTrimRule : ChangeRule
{
  public override void
    ElementPropertyChanged(ElementPropertyChangedEventArgs e)
  {
    base.ElementPropertyChanged(e);
    Comment comment = e.ModelElement as Comment;

    if (comment.Text.StartsWith(" ") || comment.Text.EndsWith(" "))
      comment.Text = comment.Text.Trim();
    // If changed, rule will trigger again.
  }
}

// Register the rule:
public partial class MyDomainModel
{
 protected override Type[] GetCustomDomainModelTypes()
 { return new Type[] { typeof(MyCommentTrimRule) };
 }
}
```

## <a name="example"></a>Příklad

### <a name="description"></a>Popis

Následující příklad přepíše obslužná rutina vlastnost vlastnosti domény a upozorní uživatele, když vlastnost `ExampleElement` došlo ke změně domény třídy.

### <a name="code"></a>Kód

```csharp
using DslModeling = global::Microsoft.VisualStudio.Modeling;
using DslDesign = global::Microsoft.VisualStudio.Modeling.Design;

namespace msft.FieldChangeSample
{
  public partial class ExampleElement
  {
    internal sealed partial class NamePropertyHandler
    {
      protected override void OnValueChanged(ExampleElement element,
         string oldValue, string newValue)
      {
        if (!this.Store.InUndoRedoOrRollback)
        {
           // make in-store changes here...
        }
        // This part is called even in undo:
        System.Windows.Forms.MessageBox.Show("Value Has Changed");
        base.OnValueChanged(element, oldValue, newValue);
      }
    }
  }
}
```