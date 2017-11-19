---
title: "Přidání vlastních vlastností do diagramů závislostí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: dependency diagrams, adding custom properties
ms.assetid: 52b3ac25-d10b-4507-a1fe-209ccb4d2777
caps.latest.revision: "21"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 130222ef3a603576f02961979e64b0c8160430af
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="add-custom-properties-to-dependency-diagrams"></a>Přidání vlastních vlastností do diagramů závislostí
Při psaní kódu rozšíření pro závislosti diagramy, můžete ukládat hodnoty s libovolný element v diagramu závislostí. Hodnoty se uchová po uložení a znovu otevřít diagram. Také může mít tyto vlastnosti se zobrazí v **vlastnosti** okna tak, aby správci zobrazit a upravit je. Například může umožní uživatelům zadat regulární výraz pro každou vrstvu a napsat kód pro ověřování k ověření, že názvy tříd v každé vrstvě shodují se vzorem zadaným uživatelem.  
  
## <a name="properties-not-visible-to-the-user"></a>Vlastnosti nejsou viditelné pro uživatele  
 Pokud chcete kód a přiřadit hodnoty libovolný element v diagramu závislostí, nemusíte definovat komponentu MEF. Je k dispozici slovník s názvem `Properties` v <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>. Stačí přidáte – zařazení hodnoty do slovníku libovolný element, vrstvy. Budou se uloží jako součást diagram závislostí. Další informace najdete v tématu [vyhledání a aktualizace modelů v programovém kódu vrstvy](../modeling/navigate-and-update-layer-models-in-program-code.md).  
  
## <a name="properties-that-the-user-can-edit"></a>Vlastnosti, které můžete upravit uživatele  
 **Počáteční přípravy**  
  
> [!IMPORTANT]
>  Chcete-li zobrazit vlastnosti, musí provést následující změnu na každém počítači, kam chcete vlastnosti vrstvy, které mají být zobrazeny.  
>   
>  1.  Spusťte program Poznámkový blok pomocí **spustit jako správce**. Otevřete`%ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest`  
> 2.  Uvnitř `Content` elementu, přidejte:  
>   
>     ```xml  
>     <MefComponent>Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.Provider.dll</MefComponent>  
>     ```  
> 3.  V části **nástroje sady Visual Studio** části sady Visual Studio aplikace nabídky start, otevřete **příkazový řádek vývojáře**.  
>   
>      Zadejte:  
>   
>      `devenv /rootSuffix /updateConfiguration`  
>   
>      `devenv /rootSuffix Exp /updateConfiguration`  
> 4.  Restartujte sadu Visual Studio.  
  
 **Ujistěte se, že váš kód je v projektu VSIX**  
  
 Pokud vaše vlastnost je částí příkaz, gesto nebo ověření projektu, nemusíte nic přidat. Kód pro vlastní vlastnost je nutné definovat v projektu Visual Studio Extensibility definované jako součást MEF. Další informace najdete v tématu [přidávání příkazů a gest do diagramů závislostí](../modeling/add-commands-and-gestures-to-layer-diagrams.md) nebo [přidání ověřování vlastní architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md).  
  
 **Definovat vlastní vlastnosti**  
  
 Chcete-li vytvořit vlastní vlastnost, definujte třídu takto:  
  
```  
[Export(typeof(IPropertyExtension))]  
public class MyProperty   
      : PropertyExtension<ILayerElement>  
{  
  // Implement the interface.  
}  
```  
  
 Můžete definovat vlastnosti na <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> ani v žádné z odvozené třídy, které zahrnují:  
  
-   `ILayerModel`-modelu  
  
-   `ILayer`-jednotlivé úrovně  
  
-   `ILayerDependencyLink`-propojení mezi vrstvami  
  
-   `ILayerComment`  
  
-   `ILayerCommentLink`  
  
## <a name="example"></a>Příklad  
 Následující kód je popisovač typické vlastní vlastnosti. Definuje vlastnost typu Boolean ve model vrstvy (`ILayerModel`), která umožňuje uživateli zadat hodnoty pro metoda vlastního ověřování.  
  
```  
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
  
## <a name="see-also"></a>Viz také  
 [Rozšíření diagramů závislostí](../modeling/extend-layer-diagrams.md)
