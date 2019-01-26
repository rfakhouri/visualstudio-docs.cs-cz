---
title: Přidání vlastních vlastností do diagramů závislostí
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom properties
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 9a3d16fda5b6a4a21ea60aaf2af3d35678e998e4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54979475"
---
# <a name="add-custom-properties-to-dependency-diagrams"></a>Přidání vlastních vlastností do diagramů závislostí

Při psaní kódu rozšíření pro diagramy závislostí můžete ukládat hodnoty libovolným prvkem na diagram závislostí. Hodnoty přetrvají i po uložení a opětovném otevření diagramu. Je také možné tyto vlastnosti zobrazit v **vlastnosti** okna tak, aby uživatelé mohou zobrazit a upravovat. Například můžete umožnit uživatelům určit regulární výraz pro každou vrstvu a psát ověřovací kód pro ověření, že názvy tříd v každé vrstvě odpovídají vzoru určenému uživatelem.

## <a name="non-visible-properties"></a>Neviditelné vlastnosti

Pokud chcete jenom váš kód k připojení k libovolnému prvku v diagramu závislost hodnoty, není nutné definovat komponentu MEF. Existuje slovník s názvem `Properties` v <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>. Stačí přidáte zařaditelné hodnoty do slovníku libovolného prvku vrstvy. Budou uloženy jako součást diagram závislostí. Další informace najdete v tématu [navigace a aktualizace modelů v programovém kódu vrstvy](../modeling/navigate-and-update-layer-models-in-program-code.md).

## <a name="editable-properties"></a>Upravitelné vlastnosti

**Počáteční Příprava**

> [!IMPORTANT]
> Chcete-li zobrazit vlastnosti, proveďte následující změnu v každém počítači, kde chcete mít viditelné vlastnosti vrstvy:
>
> 1. Spusťte program Poznámkový blok s použitím **spustit jako správce**. Otevřít *%ProgramFiles%\Microsoft Visual Studio [verze] \Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest*.
> 2. Uvnitř **obsahu** prvku, přidejte:
>
>     ```xml
>     <MefComponent>Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.Provider.dll</MefComponent>
>     ```
> 3. V části **Visual Studio Tools** části Visual Studio aplikaci nabídky start, otevřete **Developer Command Prompt**. Zadejte:
>
>      `devenv /rootSuffix /updateConfiguration`
>
>      `devenv /rootSuffix Exp /updateConfiguration`
> 4. Restartujte sadu Visual Studio.

**Ujistěte se, že je váš kód v projektu VSIX**

Pokud je vaše vlastnost součástí příkazu, gesta nebo projektu ověření, nepotřebujete nic přidat. Kód pro vlastní vlastnost by měl být definován v projektu rozšíření Visual Studio definované jako komponentu MEF. Další informace najdete v tématu [přidávání příkazů a gest do diagramů závislostí](../modeling/add-commands-and-gestures-to-layer-diagrams.md) nebo [přidání ověřování vlastní architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md).

**Definovat vlastní vlastnost**

Pokud chcete vytvořit vlastní vlastnost, definujte třídu takto:

```csharp
[Export(typeof(IPropertyExtension))]
public class MyProperty : PropertyExtension<ILayerElement>
{
  // Implement the interface.
}
```

Můžete definovat vlastnosti v <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> nebo některý z jeho odvozených tříd, mezi které patří:

-   `ILayerModel` -model

-   `ILayer` -Každá vrstva

-   `ILayerDependencyLink` -propojení mezi vrstvami

-   `ILayerComment`

-   `ILayerCommentLink`

## <a name="example"></a>Příklad

Následující kód je typický vlastní popisovač vlastnosti. Definuje booleovskou vlastnost na modelu vrstvy (`ILayerModel`), který umožňuje uživateli zadat hodnoty pro vlastní ověřovací metodu.

```csharp
using System;
using System.ComponentModel.Composition;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;

namespace MyNamespace
{
  /// <summary>
  /// Custom properties are added to the Layer Designer via a custom
  /// Property Descriptor. We have to export this Property Descriptor
  /// using MEF to make it available in the Layer Designer.
  /// </summary>
  [Export(typeof(IPropertyExtension))]
  public class AllTypesMustBeReferencedProperty
      : PropertyExtension<ILayerModel>
  {
    /// <summary>
    /// Each custom property must have a unique name.
    /// Usually we use the full name of this class.
    /// </summary>
    public static readonly string FullName =
      typeof(AllTypesMustBeReferencedProperty).FullName;

    /// <summary>
    /// Construct the property. Notice the use of FullName.
    /// </summary>
    public AllTypesMustBeReferencedProperty()
            : base(FullName)
    {  }

    /// <summary>
    /// The display name is shown in the Properties window.
    /// We therefore use a localizable resource.
    /// </summary>
    public override string DisplayName
    {
      get { return Strings.AllTypesMustBeReferencedDisplayName; }
    }

    /// <summary>
    /// Description shown at the bottom of the Properties window.
    /// We use a resource string for easier localization.
    /// </summary>
    public override string Description
    {
      get { return Strings.AllTypesMustBeReferencedDescription; }
    }

    /// <summary>
    /// This is called to set a new value for this property. We must
    /// throw an exception if the value is invalid.
    /// </summary>
    /// <param name="component">The target ILayerElement</param>
    /// <param name="value">The new value</param>
    public override void SetValue(object component, object value)
    {
      ValidateValue(value);
      base.SetValue(component, value);
    }
    /// <summary>
    /// Helper to validate the value.
    /// </summary>
    /// <param name="value">The value to validate</param>
    private static void ValidateValue(object value)
    {  }

    public override Type PropertyType
    { get { return typeof(bool); } }

    /// <summary>
    /// The segment label of the properties window.
    /// </summary>
    public override string Category
    {
      get
      {
        return Strings.AllTypesMustBeReferencedCategory;
      }
    }
  }
}
```

## <a name="see-also"></a>Viz také:

- [Rozšíření diagramů závislostí](../modeling/extend-layer-diagrams.md)
