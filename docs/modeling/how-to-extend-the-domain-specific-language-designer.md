---
title: 'Postupy: rozšíření návrháře jazyka domény | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: efcd1d354705fefcaeb0fbfbec0622ff2f06c331
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="how-to-extend-the-domain-specific-language-designer"></a>Postupy: Rozšíření návrháře jazyka specifického pro doménu
Můžete provést rozšíření návrháře, který slouží k úpravám DSL definice. Typy rozšíření, které můžete provést zahrnují přidání příkazy nabídky, přidání obslužné rutiny pro přetažení a dvakrát klikněte na gesta a pravidel, které jsou aktivované, když konkrétní typy hodnot nebo vztahy změnit. Rozšíření můžete zabalené jako Visual Studio integrace rozšíření (VSIX) a distribuovat do jiných uživatelů.  
  
 Ukázkový kód a další informace o této funkci najdete v sadě Visual Studio [vizualizace a modelování SDK (VMSDK) webu](http://go.microsoft.com/fwlink/?LinkID=186128).  
  
## <a name="setting-up-the-solution"></a>Nastavit řešení  
 Nastavte projekt, který obsahuje kód rozšíření a projekt VSIX, který exportuje projektu. Řešení může obsahovat další projekty, které jsou součástí stejné VSIX.  
  
#### <a name="to-create-a-dsl-designer-extension-solution"></a>Chcete-li vytvořit řešení rozšíření návrháře DSL  
  
1.  Vytvoření nového projektu pomocí šablony projektu knihovny tříd. V **nový projekt** dialogové okno, klikněte na tlačítko **Visual C#** a potom v okně střední, klikněte na tlačítko **knihovny tříd**.  
  
     Tento projekt bude obsahovat kód rozšíření.  
  
2.  Vytvoření nového projektu pomocí šablony projektu VSIX. V **nový projekt** dialogové okno, rozbalte seznam **Visual C#**, klikněte na tlačítko **rozšiřitelnost**a potom v prostředním okno Vyberte **projektu VSIX**.  
  
     Vyberte **přidat do řešení**.  
  
     Source.extension.vsixmanifest otevře v editoru manifestu VSIX.  
  
3.  Výše pole obsahu, klikněte na tlačítko **přidat obsahu**.  
  
4.  V **přidat obsahu** dialogové okno, sada **vyberte typ obsahu** k **Komponenta MEF**a nastavte **projektu** do projektu knihovny tříd.  
  
5.  Klikněte na tlačítko **vyberte edice** a ujistěte se, že **Visual Studio Enterprise** je zaškrtnuté.  
  
6.  Ujistěte se, že je projekt VSIX projekt po spuštění řešení.  
  
7.  V projektu knihovny tříd přidejte odkazy na následující:  
  
     Microsoft.VisualStudio.CoreUtility  
  
     Microsoft.VisualStudio.Modeling.Sdk.11.0  
  
     Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0  
  
     Microsoft.VisualStudio.Modeling.Sdk.DslDefinition.11.0  
  
     Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0  
  
     System.ComponentModel.Composition  
  
     System.Drawing  
  
     System.Drawing.Design  
  
     System.Windows.Forms  
  
## <a name="testing-and-deployment"></a>Testování a nasazení  
 Pokud chcete otestovat všechny rozšíření v tomto tématu, sestavte a spusťte řešení. Experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otevře. V tomto případě otevřete DSL řešení. DslDefinition diagram upravte. Rozšíření chování je možné zobrazit.  
  
 Nasazení rozšíření do hlavní [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]a do jiných počítačů, postupujte takto:  
  
1.  V projektu VSIX v přihrádce najít instalační soubor VSIX\\*\\\*VSIX  
  
2.  Tento soubor zkopírovat na cílový počítač a pak v Průzkumníku Windows (nebo v Průzkumníku souborů), klikněte dvakrát na jeho.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Otevře Správce rozšíření pro potvrzení, že byla nainstalovaná rozšíření.  
  
 Pokud chcete odinstalovat rozšíření, postupujte takto:  
  
1.  v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]na **nástroje** nabídky, klikněte na tlačítko **Správce rozšíření**.  
  
2.  Vyberte požadované rozšíření a odstraňte ji.  
  
## <a name="adding-a-shortcut-menu-command"></a>Přidání příkaz z místní nabídky  
 Chcete-li příkaz z místní nabídky se zobrazí na plochu návrháře DSL nebo v okně Průzkumníka DSL, napište třídu připomínající následující.  
  
 Musí implementovat třídu `ICommandExtension` a musí mít atribut `DslDefinitionModelCommandExtension`.  
  
```  
using System.Collections.Generic;  
using System.ComponentModel.Composition;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.DslDefinition;  
using Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.DslDesigner;  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;  
  
namespace Fabrikam.SimpleDslDesignerExtension  
{  
  /// <summary>  
  /// Command extending the DslDesigner.  
  /// </summary>  
  [DslDefinitionModelCommandExtension]   
  public class MyDslDesignerCommand : ICommandExtension  
  {  
    /// <summary>  
    /// Selection Context for this command  
    /// </summary>  
    [Import]  
    IVsSelectionContext SelectionContext { get; set; }  
  
    /// <summary>  
    /// Is the command visible and active?  
    /// This is called when the user right-clicks.  
    /// </summary>  
    public void QueryStatus(IMenuCommand command)  
    {  
      command.Visible = true;  
      // Is there any selected DomainClasses in the Dsl explorer?  
      command.Enabled =   
        SelectionContext.AtLeastOneSelected<DomainClass>();  
  
      // Is there any selected ClassShape on the design surface?  
      command.Enabled |=   
        (SelectionContext.GetCurrentSelection<ClassShape>()  
                .Count() > 0);  
    }  
    /// <summary>  
    /// Executes the command   
    /// </summary>  
    /// <param name="command">Command initiating this action</param>  
    public void Execute(IMenuCommand command)  
    {  
      ...  
    }  
    /// <summary>  
    /// Label for the command  
    /// </summary>  
    public string Text  
    {  
      get { return "My Command"; }  
    }  
  }  
}  
```  
  
## <a name="handling-mouse-gestures"></a>Zpracování gesta myši  
 Kód je podobný kódu příkaz nabídky.  
  
```  
[DslDefinitionModelGestureExtension]  
 class MouseGesturesExtensions : IGestureExtension  
 {  
  /// <summary>  
  /// Double-clicking on a shape representing a Domain model element displays this model element in a dialog box  
  /// </summary>  
  /// <param name="targetElement">Shape element on which the user has clicked</param>  
  /// <param name="diagramPointEventArgs">event args for this double-click</param>  
  public void OnDoubleClick(ShapeElement targetElement,  
       DiagramPointEventArgs diagramPointEventArgs)  
  {  
   ModelElement modelElement = PresentationElementHelper.  
        GetDslDefinitionModelElement(targetElement);  
   if (modelElement != null)  
   {  
    MessageBox.Show(string.Format(  
      "Double clicked on {0}", modelElement.ToString()),   
      "Model element double-clicked");  
   }  
  }  
  
  /// <summary>  
  /// Tells if the DslDesigner can consume the to-be-dropped information  
  /// </summary>  
  /// <param name="targetMergeElement">Shape on which we try to drop</param>  
  /// <param name="diagramDragEventArgs">Drop event</param>  
  /// <returns><c>true</c> if we can consume the to be dropped data, and <c>false</c> otherwise</returns>  
  public bool CanDragDrop(ShapeElement targetMergeElement,  
        DiagramDragEventArgs diagramDragEventArgs)  
  {  
   if (diagramDragEventArgs.Data.GetDataPresent(DataFormats.FileDrop))  
   {  
    diagramDragEventArgs.Effect = DragDropEffects.Copy;  
    return true;  
   }  
   return false;  
  }  
  
  /// <summary>  
  /// Processes the drop by displaying the dropped text  
  /// </summary>  
  /// <param name="targetMergeElement">Shape on which we dropped</param>  
  /// <param name="diagramDragEventArgs">Drop event</param>  
  public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)  
  {  
   if (diagramDragEventArgs.Data.GetDataPresent(DataFormats.FileDrop))  
   {  
    string[] droppedFiles =   
      diagramDragEventArgs.Data.  
               GetData(DataFormats.FileDrop) as string[];  
    MessageBox.Show(string.Format("Dropped text {0}",  
        string.Join("\r\n", droppedFiles)), "Dropped Text");  
   }  
  }  
 }  
```  
  
## <a name="responding-to-value-changes"></a>Reagovat na hodnotu změny  
 Tuto obslužnou rutinu musí modelu domény fungovala správně. Poskytujeme modelu jednoduché domény.  
  
```  
using System.Diagnostics;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.DslDefinition;  
namespace Fabrikam.SimpleDslDesignerExtension  
{  
  /// <summary>  
  /// Rule firing when the type of a domain model property is changed. The change is displayed  
  /// in the debugger (Output window of the Visual Studio instance debugging this extension)  
  /// </summary>  
  [RuleOn(typeof(PropertyHasType))]  
  public class DomainPropertyTypeChangedRule : RolePlayerChangeRule  
  {  
    /// <summary>  
    /// Method called when the Type of a Domain Property   
    /// is changed by the user in a DslDefinition  
    /// </summary>  
    /// <param name="e"></param>  
    public override void RolePlayerChanged(RolePlayerChangedEventArgs e)  
    {  
      // We are only interested in the type  
      if (e.DomainRole.Id == PropertyHasType.TypeDomainRoleId)  
      {  
        PropertyHasType relationship =   
           e.ElementLink as PropertyHasType;  
        DomainType newType = e.NewRolePlayer as DomainType;  
        DomainType oldType = e.OldRolePlayer as DomainType;  
        DomainProperty property = relationship.Property;  
  
         // We write about the Type change in the debugguer  
        Debug.WriteLine(string.Format("The type of the Domain property '{0}' of domain class '{1}' changed from '{2}' to '{3}'",  
          property.Name,  
          property.Class.Name,  
          oldType.GetFullName(false),  
          newType.GetFullName(false))  
} }  }  );  
```  
  
 Následující kód implementuje jednoduchého modelu. Vytvořte nový identifikátor GUID pro nahraďte zástupný symbol.  
  
```  
using System;  
using System.ComponentModel.Composition;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.DslDefinition;  
namespace Fabrikam.SimpleDslDesignerExtension  
{  
    /// <summary>  
    /// Simplest possible domain model   
    /// needed only for extension rules.   
    /// </summary>  
    [DomainObjectId(SimpleDomainModelExtension.DomainModelId)]  
    public class SimpleDomainModelExtension : DomainModel  
    {  
        // Id of this domain model extension   
        // Please replace this with a new GUID:  
        public const string DomainModelId =   
                  "00000000-0000-0000-0000-000000000000";  
  
        /// <summary>  
        /// Constructor for the domain model extension  
        /// </summary>  
        /// <param name="store">Store in which the domain model will be loaded</param>  
        public SimpleDomainModelExtension(Store store)  
            : base(store, new Guid(SimpleDomainModelExtension.DomainModelId))  
        {  
  
        }  
  
        /// <summary>  
        /// Rules brought by this domain model extension  
        /// </summary>  
        /// <returns></returns>  
        protected override System.Type[] GetCustomDomainModelTypes()  
        {  
            return new Type[] {  
                     typeof(DomainPropertyTypeChangedRule)  
                              };  
        }  
    }  
  
    /// <summary>  
    /// Provider for the DomainModelExtension  
    /// </summary>  
    [Export(typeof(DomainModelExtensionProvider))]    [ProvidesExtensionToDomainModel(typeof(DslDefinitionModelDomainModel))]  
    public class SimpleDomainModelExtensionProvider   
          : DomainModelExtensionProvider  
    {  
        /// <summary>  
        /// Extension model type  
        /// </summary>  
        public override Type DomainModelType  
        {  
            get  
            {  
                return typeof(SimpleDomainModelExtension);  
            }  
        }  
  
    }  
}  
```