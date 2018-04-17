---
title: Aktualizace tvarů a konektory tak, aby odrážela modelu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4c1db67cfa07afeb5427e540163ae37312a2c625
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="updating-shapes-and-connectors-to-reflect-the-model"></a>Aktualizace obrazců a konektorů k vyjádření modelu
V jazyce specifické pro doménu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], můžete provést vzhled obrazce odpovídal stavu základní model.  
  
 Příklady kódu v tomto tématu, musí být přidaní do `.cs` ve vaší `Dsl` projektu. Budete potřebovat tyto příkazy do každého souboru:  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
```  
  
## <a name="set-shape-map-properties-to-control-the-visibility-of-a-decorator"></a>Nastavit vlastnosti obrazce mapy pro řízení viditelnost dekoratéra  
 Můžete ovládat viditelnost dekoratéra bez nutnosti psaní kódu programu, nakonfigurováním mapování mezi tvar a třída domény v definici DSL. Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md).
  
## <a name="expose-the-color-and-style-of-a-shape-as-properties"></a>Vystavení barvy a stylu obrazce jako vlastnosti  
 V definici DSL, klikněte pravým tlačítkem na třídu tvaru, přejděte na **přidat zveřejněné**a pak klikněte na jednu z položek, jako **Barva výplně**.  
  
 Tvar, který má nyní vlastnosti domény, která můžete nastavit v programovém kódu nebo jako uživatel. Například pro ni nastavit v programovém kódu příkaz nebo pravidlo, můžete napsat:  
  
 `shape.FillColor = System.Drawing.Color.Red;`  
  
 Pokud chcete, aby vlastnost proměnná pouze pod kontrolou program a není uživatelem, vyberte novou vlastnost domény, jako **Barva výplně** v diagramu DSL definice. Potom v okně vlastností nastavte **je Procházet** k `false` nebo nastavte **je jen pro čtení uživatelského rozhraní** k `true`.  
  
## <a name="define-change-rules-to-make-color-style-or-location-depend-on-model-element-properties"></a>Definuje pravidla změnit barvu, styl nebo umístění, které závisí na element vlastnosti modelu  
 Můžete definovat pravidla, které aktualizují vzhled tvar, který závisí na dalších částí modelu. Například můžete definovat pravidla změnit na element modelu, který aktualizuje barva jeho závislé na vlastnostech modelu elementu obrazce. Další informace o změnit pravidla najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).  
  
 Pravidla používejte pouze k aktualizaci vlastností, které se udržují v rámci úložiště, protože pravidla nejsou volána, když se provádí příkaz Undo. Nezahrnuje některé grafické funkce, jako je například velikost a viditelnost obrazce. Chcete-li aktualizovat tyto funkce obrazce, přečtěte si téma [aktualizace bez úložiště grafické funkce](#OnAssociatedProperty).  
  
 V následujícím příkladu se předpokládá, že máte vystavení `FillColor` jako vlastnost domain, jak je popsáno v předchozí části.  
  
```csharp  
[RuleOn(typeof(ExampleElement))]  
  class ExampleElementPropertyRule : ChangeRule  
  {  
    public override void ElementPropertyChanged(ElementPropertyChangedEventArgs e)  
    {  
      base.ElementPropertyChanged(e);  
      ExampleElement element = e.ModelElement as ExampleElement;  
      // The rule is called for every property that is updated.  
      // Therefore, verify which property changed:  
      if (e.DomainProperty.Id == ExampleElement.NameDomainPropertyId)  
      {  
        // There is usually only one shape:  
        foreach (PresentationElement pel in PresentationViewsSubject.GetPresentation(element))  
        {  
          ExampleShape shape = pel as ExampleShape;  
          // Replace this with a useful condition:  
          shape.FillColor = element.Name.EndsWith("3")   
                     ? System.Drawing.Color.Red : System.Drawing.Color.Green;  
        }  
      }  
    }  
  }  
  // The rule must be registered:  
  public partial class OnAssociatedPropertyExptDomainModel  
  {  
    protected override Type[] GetCustomDomainModelTypes()  
    {  
      List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
      types.Add(typeof(ExampleElementPropertyRule));  
      // If you add more rules, list them here.   
      return types.ToArray();  
    }  
  }  
  
```  
  
## <a name="use-onchildconfigured-to-initialize-a-shapes-properties"></a>Inicializace vlastností obrazce pomocí OnChildConfigured  
 Chcete-li nastavit vlastnosti obrazce při prvním vytvoření přepsání `OnChildConfigured()` v definici částečné vaší třídy diagram. Diagram třídy je zadané ve vaší definice DSL, a generovaný kód je v **Dsl\Generated Code\Diagram.cs**. Příklad:  
  
```csharp  
partial class MyLanguageDiagram  
{  
  protected override void OnChildConfigured(ShapeElement child, bool childWasPlaced, bool createdDuringViewFixup)  
  {  
    base.OnChildConfigured(child, childWasPlaced, createdDuringViewFixup);  
    ExampleShape shape = child as ExampleShape;  
    if (shape != null)   
    {  
      if (!createdDuringViewFixup) return; // Ignore load from file.  
      ExampleElement element = shape.ModelElement as ExampleElement;  
      // Replace with a useful condition:  
      shape.FillColor = element.Name.EndsWith("3")   
          ? System.Drawing.Color.Red : System.Drawing.Color.Green;  
    }  
    // else deal with other types of shapes and connectors.  
  }  
}  
  
```  
  
 Tuto metodu můžete použít pro vlastnosti domény i bez úložiště funkce, jako je například velikost tvaru.  
  
##  <a name="OnAssociatedProperty"></a> Použít AssociateValueWith() k aktualizaci dalších funkcí obrazce  
 Pro některé funkce obrazce, jako je například, jestli má stín nebo styl šipky konektoru neexistuje žádné předdefinované metoda vystavení funkce jako vlastnost domain.  Změny na tyto funkce nejsou pod kontrolou transakcí systému. Proto není vhodné k jejich aktualizaci pomocí pravidel, protože pravidla nejsou volána, když uživatel provede příkaz Undo.  
  
 Místo toho, funkce, můžete aktualizovat pomocí <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.OnAssociatedPropertyChanged%2A>. V následujícím příkladu styl šipky konektoru řídí hodnotu vlastnosti domény v relaci, která zobrazuje konektor:  
  
```  
public partial class ArrowConnector // My connector class.   
{  
   /// <summary>  
    /// Called whenever a registered property changes in the associated model element.  
    /// </summary>  
    /// <param name="e"></param>  
    protected override void OnAssociatedPropertyChanged(VisualStudio.Modeling.Diagrams.PropertyChangedEventArgs e)  
    {  
      base.OnAssociatedPropertyChanged(e);  
      // Can be called for any property change. Therefore,  
      // Verify that this is the property we're interested in:  
      if ("IsDirected".Equals(e.PropertyName))  
      {  
        if (e.NewValue.Equals(true))  
        { // Update the shape's built-in Decorator feature:  
          this.DecoratorTo = LinkDecorator.DecoratorEmptyArrow;  
        }  
        else  
        {  
          this.DecoratorTo = null; // No arrowhead.  
        }  
      }  
    }  
    // OnAssociatedPropertyChanged is called only for properties  
    // that have been registered using AssociateValueWith().  
    // InitializeResources is a convenient place to call this.  
    // This method is invoked only once per class, even though  
    // it is an instance method.   
    protected override void InitializeResources(StyleSet classStyleSet)  
    {  
      base.InitializeResources(classStyleSet);  
      AssociateValueWith(this.Store, Wire.IsDirectedDomainPropertyId);  
      // Add other properties here.  
    }  
}  
  
```  
  
 `AssociateValueWith()` by měla být volána jednou pro každou vlastnost domény, který chcete zaregistrovat. Poté, co byla volána, všechny změny zadanou vlastnost zavolá `OnAssociatedPropertyChanged()` ve všech tvarů, která představují element vlastnosti modelu.  
  
 Není nutné volat `AssociateValueWith()` pro každou instanci. I když InitializeResources je metoda instance, je volána, pouze jednou pro každou třídu tvaru.
