---
title: "Přizpůsobení chování kopie | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87fff01c-60ba-440a-b8a0-185edcef83ac
caps.latest.revision: "16"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 532fd69bea467403047a7151584b7cf918ad602d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="customizing-copy-behavior"></a>Přizpůsobení chování kopírování
V jazyce specifické pro doménu (DSL) vytvořené pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vizualizace a modelování SDK, můžete změnit, co se stane, když uživatel zkopíruje a vloží elementy.  
  
## <a name="standard-copy-and-paste-behavior"></a>Standardní kopírování a vložení chování  
 Chcete-li povolit, kopírování, nastavte **povolit kopírování vkládání** vlastnost **Editor** uzlu v Průzkumníku DSL.  
  
 Ve výchozím nastavení pokud uživatel zkopíruje elementy do schránky, tyto prvky se také zkopírují:  
  
-   Vložené následníků vybrané elementy. (To znamená, prvky, které jsou cíle vnoření vztahy, které pocházejí v zkopíruje elementy.)  
  
-   Odkazy vztah mezi zkopírovaný elementy.  
  
 Toto pravidlo vztahuje rekurzivně zkopírovaný elementy a odkazy.  
  
 ![Zkopírovat a vložit elementy](../modeling/media/dslcopypastedefault.png "DslCopyPasteDefault")  
  
 Serializované a uložené v zkopírovaný elementy a odkazy <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype> (EGP), která je umístěna do schránky.  
  
 Obrázek elementů zkopírovaných je také umístěna do schránky. To umožňuje uživateli vložení do jiných aplikací, jako je aplikace Word.  
  
 Uživatele můžete vložit zkopírovaný prvků na cíl, který může přijmout elementy podle definice DSL. V DSL, vygenerovaná z této šablony řešení součásti, například uživatele můžete vložit porty na komponenty, ale ne do diagramu; a můžete vložit součásti do diagramu, ale ne na ostatní součásti.  
  
## <a name="customizing-copy-and-paste-behavior"></a>Přizpůsobení kopírování a vložení chování  
 Další informace o přizpůsobení modelu pomocí programu kódu najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 **Povolit nebo zakázat kopírovat, vyjmout a vložit.**  
 V Průzkumníku DSL, nastavte **povolit kopírování vkládání** vlastnost **Editor** uzlu.  
  
 **Zkopírujte odkazy na stejný cíl.** Například tak, aby měl zkopírované komentář pole Propojená stejného elementu subjektu.  
 Nastavte **rozšíří kopie** vlastnost roli tak, aby **rozšířit kopie propojit jenom**. Další informace najdete v tématu [přizpůsobení chování Kopírovat odkaz](#customizeLinks).  
  
 Zkopírujte propojené elementy. Například při kopírování nového elementu kopie všech polí propojené komentář jsou vytvářeny také.  
 Nastavte **rozšíří kopie** vlastnost roli tak, aby **rozšířit Kopírovat odkaz nebo opačnou role player**. Další informace najdete v tématu [přizpůsobení chování Kopírovat odkaz](#customizeLinks).  
  
 **Zkopírováním a vložením rychle duplicitní prvky.** Za normálních okolností je stále vybrali položku, kterou jste právě zkopírovali, a nelze vložit stejný typ elementu na něj.  
 Sloučení direktivu Element přidejte do třídy domény a nastavte ji na dopředného sloučení k nadřazené třídy. To bude mít stejný účinek na operací přetažení. Další informace najdete v tématu [přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md).  
  
 \-nebo –  
  
 Před vložením prvků, přepsáním vyberte diagram `ClipboardCommandSet.ProcessOnPasteCommand()`. Přidejte tento kód do vlastního souboru v projektu DslPackage:  
  
```csharp  
namespace Company.MyDsl {  
using System.Linq;  
using Microsoft.VisualStudio.Modeling.Diagrams;   
using Microsoft.VisualStudio.Modeling.Shell;  
partial class MyDslClipboardCommandSet  
{  
  protected override void ProcessOnMenuPasteCommand()  
  {  
 // Deselect the current selection after copying:  
 Diagram diagram = (this.CurrentModelingDocView as SingleDiagramDocView).Diagram;  
    this.CurrentModelingDocView  
     .SelectObjects(1, new object[] { diagram }, 0);  
  }  
} }  
  
```  
  
 **Když uživatel vloží do vybraných cílových, vytvořte další odkazy.** Například pokud je pole komentář vložen do elementu, odkaz se provádí mezi nimi.  
 Přidat direktivu Element sloučení k třídě cíle domény a nastavte ji zpracovat sloučení přidáním odkazy. To bude mít stejný účinek na operací přetažení. Další informace najdete v tématu [přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md).  
  
 \-nebo –  
  
 Přepsání `ClipboardCommandSet.ProcessOnPasteCommand()` po volání metody základní vytvářet další odkazy.  
  
 **Přizpůsobit formáty, ve kterých je možné zkopírovat elementy** k externím aplikacím – například přidání okraj do formuláře rastrového obrázku.  
 Přepsání *MyDsl* `ClipboardCommandSet.ProcessOnMenuCopyCommand()` v DslPackage projektu.  
  
 **Přizpůsobte, jak jsou elementy zkopírován do schránky příkazem kopírování, ale není v rámci operace přetažení.**  
 Přepsání *MyDsl* `ClipboardCommandSet.CopyModelElementsIntoElementGroupPrototype()` v DslPackage projektu.  
  
 **Zachovat tvar rozložení prostřednictvím kopírování a vkládání.**  
 Když uživatel kopie více tvarů, když budou vložena lze zachovat jejich relativní umístění. Tento postup je znázorněn příklad v [VMSDK: Ukázka okruhů](http://go.microsoft.com/fwlink/?LinkId=213879).  
  
 K dosažení tohoto efektu, přidejte do zkopírovaný ElementGroupPrototype tvarů a konektory. Nejvíce vhodnou metodu pro přepsání je ElementOperations.CreateElementGroupPrototype(). Chcete-li to provést, přidejte následující kód do projektu Dsl:  
  
```csharp  
  
public class MyElementOperations : DesignSurfaceElementOperations  
{  
  // Create an EGP to add to the clipboard.  
  // Called when the elements to be copied have been  
  // collected into an ElementGroup.  
 protected override ElementGroupPrototype CreateElementGroupPrototype(ElementGroup elementGroup, ICollection<ModelElement> elements, ClosureType closureType)  
  {  
 // Add the shapes and connectors:  
 // Get the elements already in the group:  
    ModelElement[] mels = elementGroup.ModelElements  
        .Concat(elementGroup.ElementLinks) // Omit if the paste target is not the diagram.  
        .ToArray();  
 // Get their shapes:  
    IEnumerable<PresentationElement> shapes =   
       mels.SelectMany(mel =>   
            PresentationViewsSubject.GetPresentation(mel));  
    elementGroup.AddRange(shapes);  
  
 return base.CreateElementGroupPrototype  
           (elementGroup, elements, closureType);  
  }  
  
 public MyElementOperations(IServiceProvider serviceProvider, ElementOps1Diagram diagram)  
      : base(serviceProvider, diagram)  
  { }  
}  
  
// Replace the standard ElementOperations  
// singleton with your own:  
partial class MyDslDiagram // EDIT NAME  
{  
 /// <summary>  
 /// Singleton ElementOperations attached to this diagram.  
 /// </summary>  
 public override DesignSurfaceElementOperations ElementOperations  
  {  
 get  
    {  
 if (singleton == null)  
      {  
        singleton = new MyElementOperations(this.Store as IServiceProvider, this);  
      }  
 return singleton;  
    }  
  }  
 private MyElementOperations singleton = null;  
}  
  
```  
  
 **Vkládání obrazců do zvoleného umístění, jako je například aktuálním umístěním kurzoru.**  
 Když uživatel kopie více tvarů, když budou vložena lze zachovat jejich relativní umístění. Tento postup je znázorněn příklad v [VMSDK: Ukázka okruhů](http://go.microsoft.com/fwlink/?LinkId=213879).  
  
 K dosažení tohoto efektu, přepsání `ClipboardCommandSet.ProcessOnMenuPasteCommand()` používat konkrétní umístění verzi `ElementOperations.Merge()`. Chcete-li to provést, přidejte následující kód v projektu DslPackage:  
  
```csharp  
  
partial class MyDslClipboardCommandSet // EDIT NAME  
{  
   /// <summary>  
    /// This method assumes we only want to paste things onto the diagram  
    /// - not onto anything contained in the diagram.  
    /// The base method pastes in a free space on the diagram.  
    /// But if the menu was used to invoke paste, we want to paste in the cursor position.  
    /// </summary>  
    protected override void ProcessOnMenuPasteCommand()  
    {  
  
  NestedShapesSampleDocView docView = this.CurrentModelingDocView as NestedShapesSampleDocView;  
  
      // Retrieve data from clipboard:  
      System.Windows.Forms.IDataObject data = System.Windows.Forms.Clipboard.GetDataObject();  
  
      Diagram diagram = docView.CurrentDiagram;  
      if (diagram == null) return;  
  
      if (!docView.IsContextMenuShowing)  
      {  
        // User hit CTRL+V - just use base method.  
  
        // Deselect anything that's selected, otherwise  
        // pasted item will be incompatible:  
        if (!this.IsDiagramSelected())  
        {  
          docView.SelectObjects(1, new object[] { diagram }, 0);  
        }  
  
        // Paste into a convenient spare space on diagram:  
    base.ProcessOnMenuPasteCommand();  
      }  
      else  
      {  
        // User right-clicked - paste at mouse position.  
  
        // Utility class:  
        DesignSurfaceElementOperations op = diagram.ElementOperations;  
  
        ShapeElement pasteTarget = diagram;  
  
        // Check whether what's in the paste buffer is acceptable on the target.  
        if (pasteTarget != null && op.CanMerge(pasteTarget, data))  
        {  
  
        // Although op.Merge would be a no-op if CanMerge failed, we check CanMerge first  
          // so that we don't create an empty transaction (after which Undo would be no-op).  
          using (Transaction t = diagram.Store.TransactionManager.BeginTransaction("paste"))  
          {  
            PointD place = docView.ContextMenuMousePosition;  
            op.Merge(pasteTarget, data, PointD.ToPointF(place));  
            t.Commit();  
          }  
        }  
      }  
    }  
  }  
```  
  
 **Umožní uživateli přetažení elementy.**  
 V tématu [postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md).  
  
##  <a name="customizeLinks"></a>Přizpůsobení chování Kopírovat odkaz  
 Když uživatel kopie elementu, standardní chování je, že jsou všechny vložené prvky také zkopírován. Standardní chování kopírování, můžete upravit. V definici DSL vybrat roli na jedné straně relace a v sadě okno Vlastnosti **rozšíří kopie** hodnotu.  
  
 ![Rozšíří vlastnost kopírování role domény](../modeling/media/dslpropagatescopy.png "DslPropagatesCopy")  
  
 Existují tři hodnoty:  
  
-   Nešířily kopie  
  
-   Rozšíří kopie propojit jenom - skupině Po vložení, nové kopie tento odkaz bude odkazovat na existující element na druhém konci odkazu.  
  
-   Rozšíří kopie propojení a opačným role player - zkopírovaný skupina obsahuje kopii elementu na druhém konci odkazu.  
  
 ![Účinek kopírování s PropagateCopyToLinkOnly](../modeling/media/dslpropagatecopy.png "DslPropagateCopy")  
  
 Elementy a bitovou kopii, která se zkopírují, bude mít vliv změny, které provedete.  
  
## <a name="programming-copy-and-paste-behavior"></a>Programování kopírování a vložení chování  
 Mnoho aspektů chování DSL s ohledem na kopírování, vkládání, vytvoření nebo odstranění objektů se řídí instanci <xref:Microsoft.VisualStudio.Modeling.ElementOperations> který je připojen diagramu. Můžete upravit chování vaší DSL odvozením vlastní třídy z <xref:Microsoft.VisualStudio.Modeling.ElementOperations> a přepsáním <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.ElementOperations%2A> vlastnost třídě diagram.  
  
> [!TIP]
>  Další informace o přizpůsobení modelu pomocí programu kódu najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 ![Diagram pořadí operace kopírování](../modeling/media/dslcopyseqdiagram.png "dslCopySeqDiagram")  
  
 ![Diagram pořadí operaci vložení](../modeling/media/dslpasteseqdiagram.png "dslPasteSeqDiagram")  
  
#### <a name="to-define-your-own-elementoperations"></a>Chcete-li definovat vlastní ElementOperations  
  
1.  Do nového souboru ve vašem projektu DSL, vytvořte třídu, která je odvozená od <xref:Microsoft.VisualStudio.Modeling.Diagrams.DesignSurfaceElementOperations>.  
  
2.  Přidejte třídu definice pro třídu diagram. Název této třídy naleznete v **Dsl\GeneratedCode\Diagrams.cs**.  
  
     Ve třídě diagram přepsat <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.ElementOperations%2A> vrátit instanci vaše ElementOperations podtřída. By měl vrátit stejnou instanci v každém volání.  
  
 Přidejte tento kód v souboru vlastního kódu v projektu DslPackage:  
  
```csharp  
  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;  
  
  public partial class MyDslDiagram  
  {  
    public override DesignSurfaceElementOperations ElementOperations  
    {  
      get  
      {  
        if (this.elementOperations == null)  
        {  
          this.elementOperations = new MyElementOperations(this.Store as IServiceProvider, this);  
        }  
        return this.elementOperations;  
      }  
    }  
    private MyElementOperations elementOperations = null;  
  }  
  
  public class MyElementOperations : DesignSurfaceElementOperations  
  {  
    public MyElementOperations(IServiceProvider serviceProvider, MyDslDiagram diagram)  
      : base(serviceProvider, diagram)  
    { }  
    // Overridden methods follow  
  }  
  
```  
  
## <a name="receiving-items-dragged-from-other-models"></a>Přijetí položky přetažením z jiných modelů  
 ElementOperations lze také definovat chování kopírovat, přesunout, odstranění a přetažení myší. Jako ukázka použití ElementOperations zde příkladě definuje vlastní chování přetažení myší. Však k tomuto účelu můžete zvážit alternativní metody uvedené v [postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md), což je více extensible.  
  
 Definujte dvě metody ve třídě ElementOperations:  
  
-   `CanMerge(ModelElement targetElement, System.Windows.Forms.IDataObject data)`který určuje, zda může být source element přetáhli cíl tvaru, konektoru nebo diagram.  
  
-   `MergeElementGroupPrototype(ModelElement targetElement, ElementGroupPrototype sourcePrototype)`source element který spojuje do cílové.  
  
### <a name="canmerge"></a>CanMerge()  
 `CanMerge()`je volána k určení zpětnou vazbu, která má být poskytnut uživateli při pohybu myší v diagramu. Parametry metody jsou element, za které je ukazatele myši a data o zdroj, ze které byla provedena operace přetažení. Uživatele můžete přetáhnout z kdekoli na obrazovce. Zdrojový objekt proto může být mnoho různých typů a může být serializována v různých formátech. Pokud je zdroj DSL nebo UML modelu, parametr dat je serializaci <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>. Operace přetažení, kopírování a sady nástrojů pomocí ElementGroupPrototypes znázornit fragmenty modelů.  
  
 Prototypu skupiny Element může obsahovat libovolný počet elementů a odkazy. Typy prvků lze identifikovat podle identifikátorů GUID. Identifikátor GUID je obrazec, který byl přetáhli, není základní element modelu. V následujícím příkladu `CanMerge()` vrátí hodnotu true, pokud je třída tvaru z diagramu UML přetáhli tohoto diagramu.  
  
```csharp  
public override bool CanMerge(ModelElement targetShape, System.Windows.Forms.IDataObject data)  
 {  
  // Extract the element prototype from the data.  
  ElementGroupPrototype prototype = ElementOperations.GetElementGroupPrototype(this.ServiceProvider, data);  
  if (targetShape is MyTargetShape && prototype != null &&  
        prototype.RootProtoElements.Any(rootElement =>   
          rootElement.DomainClassId.ToString()   
          ==  "3866d10c-cc4e-438b-b46f-bb24380e1678")) // Guid of UML Class shapes  
          // or SourceClass.DomainClassId  
        return true;  
   return base.CanMerge(targetShape, data);  
 }  
  
```  
  
## <a name="mergeelementgroupprototype"></a>MergeElementGroupPrototype()  
 Tato metoda je volána, když uživatel zahodí element na diagram, obrazce nebo konektor. Ho měli sloučit taženou obsah do cílového elementu. V tomto příkladu kód určuje, zda rozpoznala kombinaci typů cíle a prototypu; Pokud ano, metoda převede taženou elementy prototyp elementy, které mají být přidány do modelu. Základní metoda je volána k provedení sloučení, buď elementů převedený nebo nepřevedeném.  
  
```csharp  
public override void MergeElementGroupPrototype(ModelElement targetShape, ElementGroupPrototype sourcePrototype)  
{  
  ElementGroupPrototype prototypeToMerge = sourcePrototype;  
  MyTargetShape pel = targetShape as MyTargetShape;  
  if (pel != null)  
  {  
    prototypeToMerge = ConvertDraggedTypeToLocal(pel, sourcePrototype);  
  }  
  if (prototypeToMerge != null)  
    base.MergeElementGroupPrototype(targetShape, prototypeToMerge);  
}  
  
```  
  
 V tomto příkladu se zabývá elementů třída UML přetažením z diagramu tříd UML. DSL není určen k ukládání tříd UML přímo, ale místo toho vytvoříme DSL element pro každou taženou UML třídu. To bude užitečná, například když DSL je diagramu instance. Uživatel může přetažením třídy na diagram pro vytvoření instancí těchto tříd.  
  
```csharp  
  
private ElementGroupPrototype ConvertDraggedTypeToLocal (MyTargetShape snapshot, ElementGroupPrototype prototype)  
{  
  // Find the UML project:  
  EnvDTE.DTE dte = snapshot.Store.GetService(typeof(EnvDTE.DTE)) as EnvDTE.DTE;  
  foreach (EnvDTE.Project project in dte.Solution.Projects)  
  {  
    IModelingProject modelingProject = project as IModelingProject;  
    if (modelingProject == null) continue; // not a modeling project  
    IModelStore store = modelingProject.Store;  
    if (store == null) continue;  
    // Look for the shape that was dragged:  
    foreach (IDiagram umlDiagram in store.Diagrams())  
    {  
      // Get modeling diagram that implements UML diagram:  
      Diagram diagram = umlDiagram.GetObject<Diagram>();  
      Guid elementId = prototype.SourceRootElementIds.FirstOrDefault();  
      ShapeElement shape = diagram.Partition.ElementDirectory.FindElement(elementId) as ShapeElement;  
      if (shape == null) continue;  
      IClass classElement = shape.ModelElement as IClass;  
      if (classElement == null) continue;  
  
      // Create a prototype of elements in my DSL, based on the UML element:  
      Instance instance = new Instance(snapshot.Store);  
      instance.Type = classElement.Name;  
      // Pack them into a prototype:  
      ElementGroup group = new ElementGroup(instance);  
      return group.CreatePrototype();  
    }  
  }  
  return null;  
}  
  
```  
  
## <a name="standard-copy-behavior"></a>Standardní kopie chování  
 Kód v této části ukazuje, že ke změně kopírování chování můžete přepsat metody, které si chcete. Můžete zjistit, jak dosáhnout vlastní úpravy, tato část ukazuje kód, který přepíše metody účastnící se kopírování, ale nemění standardní chování.  
  
 Když uživatel stiskne klávesu CTRL + C nebo používá příkaz nabídky kopie metodu <xref:Microsoft.VisualStudio.Modeling.Shell.ClipboardCommandSet.ProcessOnMenuCopyCommand%2A> je volána. Uvidíte, jak toto nastavení **DslPackage\Generated Code\CommandSet.cs**. Další informace o tom, jak jsou příkazy nastavení najdete v tématu [postupy: přidání příkazu do místní nabídky](../modeling/how-to-add-a-command-to-the-shortcut-menu.md).  
  
 ProcessOnMenuCopyCommand můžete přepsat tak, že přidáte definice třídu *MyDsl* `ClipboardCommandSet` v DslPackage projektu.  
  
```csharp  
using System.Collections.Generic;  
using System.Drawing;  
using System.Windows.Forms;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
partial class MyDslClipboardCommandSet  
{  
  /// <summary>  
  /// Override ProcessOnMenuCopyCommand() to copy elements to the  
  /// clipboard in different formats, or to perform additional tasks  
  /// before or after copying - for example deselect the copied elements.  
  /// </summary>  
  protected override void ProcessOnMenuCopyCommand()  
  {  
    IList<ModelElement> selectedModelElements = this.SelectedElements;  
    if (selectedModelElements.Count == 0) return;  
  
    // System container for clipboard data.  
    // The IDataObject can contain data in several formats.  
    IDataObject dataObject = new DataObject();  
  
    Bitmap bitmap = null; // For export to other programs.  
    try  
    {  
      #region Create EGP for copying to a DSL.  
      this.CopyModelElementsIntoElementGroupPrototype  
                     (dataObject, selectedModelElements);  
      #endregion  
  
      #region Create bitmap for copying to another application.   
      // Find all the shapes associated with this selection:  
      List<ShapeElement> shapes = new List<ShapeElement>(  
        this.ResolveExportedShapesForClipboardImages  
              (dataObject, selectedModelElements));  
  
      bitmap = this.CreateBitmapForClipboard(shapes);  
      if (bitmap != null)  
      {  
        dataObject.SetData(DataFormats.Bitmap, bitmap);  
      }  
      #endregion   
  
      // Add the data to the clipboard:  
      Clipboard.SetDataObject(dataObject, true, 5, 100);  
    }  
    finally  
    {  
      // Dispose bitmap after SetDataObject:  
      if (bitmap != null) bitmap.Dispose();  
    }  
  }  
/// <summary>  
/// Override this to customize the element group that is copied to the clipboard.  
/// </summary>  
protected override void CopyModelElementsIntoElementGroupPrototype(IDataObject dataObject, IList<ModelElement> selectedModelElements)  
{  
  return this.ElementOperations.Copy(dataObject, selectedModelElements);  
}  
}  
```  
  
 Každý diagram má instanci typu singleton daného ElementOperations. Můžete zadat vlastní odvozených. Tento soubor, který můžete umístit v projektu DSL, se budou chovat stejný jako kód, který přepíše:  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
namespace Company.MyDsl  
{  
  partial class MyDslDiagram  
  {  
    /// <summary>  
    /// Singleton ElementOperations attached to this diagram.  
    /// </summary>  
    public override DesignSurfaceElementOperations ElementOperations  
    {  
      get  
      {  
        if (this.elementOperations == null)  
        {  
          this.elementOperations = new MyElementOperations(this.Store as IServiceProvider, this);  
        }  
        return this.elementOperations;  
      }  
    }  
    private MyElementOperations elementOperations = null;  
  }  
  
  // Our own version of ElementOperations so that we can override:  
  public class MyElementOperations : DesignSurfaceElementOperations  
  {  
    public MyElementOperations(IServiceProvider serviceProvider, ElementOps1Diagram diagram)  
      : base(serviceProvider, diagram)  
    { }  
  
    /// <summary>  
    /// Copy elements to the clipboard data.  
    /// Provides a hook for adding custom data.  
    /// </summary>  
    public override void Copy(System.Windows.Forms.IDataObject data,   
      ICollection<ModelElement> elements,   
      ClosureType closureType,   
      System.Drawing.PointF sourcePosition)  
    {  
      if (CanAddElementGroupFormat(elements, closureType))  
      {  
        AddElementGroupFormat(data, elements, closureType);   
      }  
  
      // Override these to store additional data:  
      if (CanAddCustomFormat(elements, closureType))  
      {  
        AddCustomFormat(data, elements, closureType, sourcePosition);  
      }  
    }  
  
    protected override void AddElementGroupFormat(System.Windows.Forms.IDataObject data, ICollection<ModelElement> elements, ClosureType closureType)  
    {  
      // Add the selected elements and those implied by the propagate copy rules:  
      ElementGroup elementGroup = this.CreateElementGroup(elements, closureType);  
  
      // Mark all the elements that are not embedded under other elements:  
      this.MarkRootElements(elementGroup, elements, closureType);  
  
      // Store in the clipboard data:  
      ElementGroupPrototype elementGroupPrototype = this.CreateElementGroupPrototype(elementGroup, elements, closureType);  
      data.SetData(ElementGroupPrototype.DefaultDataFormatName, elementGroupPrototype);  
    }  
  
    /// <summary>  
    /// Override this to store additional elements in the element group:  
    /// </summary>  
    protected override ElementGroupPrototype CreateElementGroupPrototype(ElementGroup elementGroup, ICollection<ModelElement> elements, ClosureType closureType)  
    {  
      ElementGroupPrototype prototype = new ElementGroupPrototype(this.Partition, elementGroup.RootElements, elementGroup);  
      return prototype;  
    }  
  
    /// <summary>  
    /// Create an element group from the given starting elements, using the   
    /// copy propagation rules specified in the DSL Definition.  
    /// By default, this includes all the embedded descendants of the starting elements,  
    /// and also includes reference links where both ends are already included.  
    /// </summary>  
    /// <param name="startElements">model elements to copy</param>  
    /// <param name="closureType"></param>  
    /// <returns></returns>  
    protected override ElementGroup CreateElementGroup(ICollection<ModelElement> startElements, ClosureType closureType)  
    {  
      // ElementClosureWalker finds all the connected elements,   
      // according to the propagate copy rules specified in the DSL Definition:  
      ElementClosureWalker walker = new ElementClosureWalker(this.Partition,   
        closureType, // Normally ClosureType.CopyClosure  
        startElements,   
        true, // Do not load other models.  
        null, // Optional list of domain roles not to traverse.  
        true); // Include relationship links where both ends are already included.  
  
      walker.Traverse(startElements);  
      IList<ModelElement> closureList = walker.ClosureList;  
      Dictionary<object, object> closureContext = walker.Context;  
  
      // create a group for this closure  
      ElementGroup group = new ElementGroup(this.Partition);  
      group.AddRange(closureList, false);  
  
      // create the element group prototype for the group  
      foreach (object key in closureContext.Keys)  
      {  
        group.SourceContext.ContextInfo[key] = closureContext[key];  
      }  
  
      return group;  
    }  
  }  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md)   
 [Postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Přizpůsobení chování při odstranění](../modeling/customizing-deletion-behavior.md)   
 [Ukázka: Ukázka VMSDK okruhů](http://go.microsoft.com/fwlink/?LinkId=213879)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
 
