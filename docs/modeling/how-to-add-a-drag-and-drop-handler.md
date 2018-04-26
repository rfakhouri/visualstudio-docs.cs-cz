---
title: 'Postupy: Přidání obslužné rutiny operace přetažení myší'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: a777c837b6bf33c44ac27e7307f3e0354e3a9c3a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-a-drag-and-drop-handler"></a>Postupy: Přidání obslužné rutiny operace přetažení myší
Obslužné rutiny události přetažení myší můžete přidat do vaší DSL tak, aby uživatelé můžete přetáhnout položky na diagramu z jiných diagramů nebo z různých částí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Můžete také přidat obslužné rutiny pro události, jako poklikáním. Společně přetahování myší a dvojitým kliknutím obslužné rutiny se označují jako *gesty obslužné rutiny*.

 Toto téma popisuje gesta přetahování myší, které pocházejí v jiných diagramech. Pro přesunutí a zkopírujte události v rámci jedné diagram, zvažte alternativní definice podtřídou třídy `ElementOperations`. Další informace najdete v tématu [přizpůsobení chování kopie](../modeling/customizing-copy-behavior.md). Také je možné upravit definici DSL.

## <a name="in-this-topic"></a>V tomto tématu

-   První dvě části popisují alternativní metody definování obslužné rutiny gest:

    -   [Definování obslužné rutiny gesto metodami přepsání ShapeElement](#overrideShapeElement). `OnDragDrop`, `OnDoubleClick`, `OnDragOver`, a další metody lze přepsat.

    -   [Definování obslužné rutiny gesto pomocí MEF](#MEF). Tuto metodu použijte, pokud chcete, aby třetí strany vývojáři mohli definovat svoje vlastní obslužné rutiny pro vaše DSL. Uživatelé mohou po instalováni vaší DSL instalace rozšíření jiných výrobců.

-   [Dekódování Taženou položku](#extracting). Prvky můžete přetáhnout z kteréhokoli okna nebo z plochy, ale také DSL.

-   [Jak získat původní přetáhnout položky](#getOriginal). Pokud taženou položku je DSL element, můžete otevřít zdrojový model a přístup k elementu.

-   [Pomocí akce myši: Přetáhnete položky prostředí](#mouseActions). Tento příklad znázorňuje nižší úrovně obslužná rutina, která zabrání akce myši na pole obrazce. V příkladu umožňuje uživateli změnit pořadí položek v prostoru přetažením pomocí myši.

##  <a name="overrideShapeElement"></a> Definování obslužné rutiny gesto přepsáním metody ShapeElement
 Přidáte nový soubor kódu do projektu DSL. Pro obslužné rutiny gest, je obvykle musí mít minimálně následující `using` příkazy:

```csharp
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;
using System.Linq;
```

 V novém souboru definice částečné třídy pro tvar nebo diagram třídu, která má odpovědět na operaci přetažení. Přepište tyto metody:

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.OnDragOver%2A>– Tato metoda je volána, když ukazatel myši zadá tvaru během operace přetažení. Metodu by měl zkontrolovat položku, je přetáhnete uživatele a nastavte vlastnost účinek indikující, zda uživatel mohou vyřadit položky na tento tvar. Vlastnost účinek určuje vzhled kurzor, zatímco je přes tento tvar a také určuje, zda `OnDragDrop()` bude volána, když uživatel uvolní tlačítko myši.

    ```csharp
    partial class MyShape // MyShape generated from DSL Definition.
    {
        public override void OnDragOver(DiagramDragEventArgs e)
        {
          base.OnDragOver(e);
          if (e.Effect == System.Windows.Forms.DragDropEffects.None
               && IsAcceptableDropItem(e)) // To be defined
          {
            e.Effect = System.Windows.Forms.DragDropEffects.Copy;
          }
        }

    ```

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.OnDragDrop%2A> – Tato metoda je volána, pokud uživatel uvolní tlačítko myši při ponecháte ukazatel myši nad tento tvar nebo diagram, pokud `OnDragOver(DiagramDragEventArgs e)` dříve nastavené `e.Effect` hodnotu jinou než `None`.

    ```csharp
    public override void OnDragDrop(DiagramDragEventArgs e)
        {
          if (!IsAcceptableDropItem(e))
          {
            base.OnDragDrop(e);
          }
          else
          { // Process the dragged item, for example merging a copy into the diagram
            ProcessDragDropItem(e); // To be defined
          }
        }

    ```

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.OnDoubleClick%2A> – Tato metoda je volána při poklepání tvar nebo diagram.

     Další informace najdete v tématu [postupy: zachycení a klikněte na tvar nebo Dekoratéra](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md).

 Definování `IsAcceptableDropItem(e)` určit, jestli je přijatelné taženou položku a ProcessDragDropItem(e) k aktualizaci modelu, když položka byla vynechána. Tyto metody musí nejprve extrahovat položku z argumenty událostí. Informace o tom, jak to udělat najdete v tématu [jak získat odkaz na taženou položku](#extracting).

##  <a name="MEF"></a> Definování obslužné rutiny gesto pomocí rozhraní MEF
 MEF (spravované rozhraní rozšiřitelnosti) umožňuje definovat součásti, které je možné nainstalovat s minimální konfigurací. Další informace najdete v tématu [Managed Extensibility Framework (MEF)](/dotnet/framework/mef/index).

#### <a name="to-define-a-mef-gesture-handler"></a>Chcete-li definovat obslužné rutiny gest MEF

1.  Přidat do vaší **Dsl** a **DslPackage** projekty **MefExtension** soubory, které jsou popsané v [rozšíření vaší DSL pomocí MEF](../modeling/extend-your-dsl-by-using-mef.md).

2.  Nyní je možné definovat obslužné rutiny gest jako součást MEF:

    ```

    // This attribute is defined in the generated file
    // DslPackage\MefExtension\DesignerExtensionMetaDataAttribute.cs:
    [MyDslGestureExtension]
    public class MyGestureHandlerClassName : IGestureExtension
    {
      /// <summary>
      /// Called to determine whether a drag onto the diagram can be accepted.
      /// </summary>
      /// <param name="diagramDragEventArgs">Contains a link to the item that is being dragged</param>
      /// <param name="targetMergeElement">The shape or connector that the mouse is over</param>
      /// <returns>True if the item can be accepted on the targetMergeElement.</returns>
      public bool CanDragDrop(ShapeElement targetMergeElement, DiagramDragEventArgs diagramDragEventArgs)
      {
        MyShape target = targetMergeElement as MyShape;
        if (target == null) return false;
        if (target.IsAcceptableDropItem(diagramDragEventArgs)) return true;
        return false;
      }
      public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)
      {
        MyShape target = targetMergeElement as MyShape;
        if (target == null || ! target.IsAcceptableDropItem(diagramDragEventArgs)) return;
        // Process the dragged item, for example merging a copy into the diagram:
        target.ProcessDragDropItem(diagramDragEventArgs);
     }

    ```

     Můžete vytvořit více než jedna součást obslužná rutina gesto, například pokud máte různé typy taženou objektů.

3.  Přidání definic třídu pro cíl tvaru, konektoru nebo diagramu tříd a definovat metody `IsAcceptableDropItem()` a `ProcessDragDropItem()`. Tyto metody musí začínat extrahováním taženou položku z argumenty událostí. Další informace najdete v tématu [jak získat odkaz na taženou položku](#extracting).

##  <a name="extracting"></a> Dekódování taženou položku
 Když uživatel nastavuje tažením položku do diagramu, nebo z jedné části diagramu na jiný, je k dispozici v informace o položce, který je právě přetáhli `DiagramDragEventArgs`. Protože operace tažení může spustili na libovolného objektu na obrazovce, data mohou být k dispozici v některém z mnoha různých formátech. Váš kód uzná formáty, se kterými je schopen práci.

 Chcete-li zjistit formátů, ve kterých vaše informace o zdroji přetáhněte je k dispozici, spusťte kódu v ladění režimu, nastavení boru přerušení na záznam, který má `OnDragOver()` nebo `CanDragDrop()`. Zkontrolujte hodnoty `DiagramDragEventArgs` parametr. Informace jsou poskytovány ve dvou formách:

-   <xref:System.Windows.Forms.IDataObject>  `Data` – Tato vlastnost představuje serializovaných verzích zdrojové objekty, obvykle ve více než jeden formátu. Své nejužitečnější funkce jsou:

    -   diagramEventArgs.Data.GetDataFormats() - obsahuje seznam formátů, ve kterých může dekódovat taženou objektu. Například pokud uživatel nastavuje tažením soubor z plochy, k dispozici jsou název souboru ("`FileNameW`").

    -   `diagramEventArgs.Data.GetData(format)` -Dekóduje taženou objekt v zadaném formátu. Objekt odpovídající typ přetypování. Příklad:

         `string fileName = diagramEventArgs.Data.GetData("FileNameW") as string;`

         Objekty, jako jsou odkazy na sběrnici model ze zdroje může taky přenášet ve vlastní formát. Další informace najdete v tématu [postup odesílání modelu sběrnice odkazů v operace přetažení](#mbr).

-   <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype> `Prototype` – Pokud chcete, aby uživatelé přetahování položek z DSL nebo modelu UML pomocí této vlastnosti. K elementu skupiny prototypu obsahuje jeden nebo více objektů, odkazy a jejich hodnoty vlastností. Používá se také v operace vložení a když přidáváte element z panelu nástrojů. V prototyp objekty a jejich typy jsou označeny identifikátor Guid. Tento kód například umožňuje uživateli přetáhněte prvků třídy z UML diagram nebo Průzkumníka modelu UML:

    ```csharp
    private bool IsAcceptableDropItem(DiagramDragEventArgs e)
    {
      return e.Prototype != null && e.Prototype.RootProtoElements.Any(element =>
            element.DomainClassId.ToString()
            == "3866d10c-cc4e-438b-b46f-bb24380e1678"); // Accept UML class shapes.
     // Or, from another DSL: SourceNamespace.SourceShapeClass.DomainClassId
    }

    ```

     Přijmout obrazce UML, určete identifikátory GUID tvar tříd UML pomocí experimentu. Mějte na paměti, se obvykle více než jeden typ elementu v jakékoli diagramu. Nezapomeňte také, zda je objekt přetažením z diagramu DSL nebo UML tvaru, není element modelu.

 `DiagramDragEventArgs` také obsahuje vlastnosti, které označují aktuální umístění ukazatele myši a zda je uživatel stisknutím CTRL, ALT nebo SHIFT – klávesy.

##  <a name="getOriginal"></a> Jak získat původní taženou elementu
 `Data` a `Prototype` vlastnosti argumenty událostí obsahovat pouze odkaz na taženou tvaru. Obvykle Pokud chcete vytvořit objekt v cílové DSL, který je odvozený z prototypu nějakým způsobem, budete muset získat přístup k původní, například čtení obsah souboru nebo přechod na element modelu reprezentována obrazce.  Visual Studio modelu sběrnice můžete použít usnadní to.

### <a name="to-prepare-a-dsl-project-for-model-bus"></a>Příprava projektu DSL pro Model sběrnice

1.  Zpřístupněte zdroji DSL podle [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] modelu sběrnice:

    1.  Stáhněte a nainstalujte Visual Studio modelu sběrnice rozšíření, pokud již není nainstalována. Další informace najdete v tématu [vizualizace a modelování SDK](http://go.microsoft.com/fwlink/?LinkID=185579).

    2.  Otevřete soubor definice DSL zdroje DSL v Návrháři DSL. Klikněte pravým tlačítkem na návrhovou plochu a potom klikněte na **povolit Modelbus**. V dialogovém okně, vyberte jednu nebo obě možnosti.  Click **OK**. Nový projekt "ModelBus" je přidán do DSL řešení.

    3.  Klikněte na tlačítko **transformaci všech šablon** a znovu sestavte řešení.

###  <a name="mbr"></a> Odesílat objekt ze zdroje DSL

1.  V vaše podtřída ElementOperations přepsat `Copy()` tak, aby ho kóduje sběrnice referenční Model (MBR) do IDataObject. Tato metoda bude volána při spuštění uživatelem přetáhněte z diagram zdroje. Kódovaného MBR bude k dispozici v IDataObject, jakmile uživatel přesune v diagramu cíl.

    ```

    using Microsoft.VisualStudio.Modeling;
    using Microsoft.VisualStudio.Modeling.Shell;
    using Microsoft.VisualStudio.Modeling.Diagrams;
    using Microsoft.VisualStudio.Modeling.Integration;
    using Microsoft.VisualStudio.Modeling.Integration.Shell;
    using System.Drawing; // PointF
    using  System.Collections.Generic; // ICollection
    using System.Windows.Forms; // for IDataObject
    ...
    public class MyElementOperations : DesignSurfaceElementOperations
    {
        public override void Copy(System.Windows.Forms.IDataObject data, System.Collections.Generic.ICollection<ModelElement> elements, ClosureType closureType, System.Drawing.PointF sourcePosition)
        {
          base.Copy(data, elements, closureType, sourcePosition);

          // Get the ModelBus service:
          IModelBus modelBus =
              this.Store.GetService(typeof(SModelBus)) as IModelBus;
          DocData docData = ((VSDiagramView)this.Diagram.ActiveDiagramView).DocData;
          string modelFile = docData.FileName;
          // Get an adapterManager for the target DSL:
          ModelBusAdapterManager manager =
              (modelBus.FindAdapterManagers(modelFile).First());
          ModelBusReference modelReference = manager.CreateReference(modelFile);
          ModelBusReference elementReference = null;
          using (ModelBusAdapter adapter = modelBus.CreateAdapter(modelReference))
          {
            elementReference = adapter.GetElementReference(elements.First());
          }

          data.SetData("ModelBusReference", elementReference);
        }
    ...}

    ```

### <a name="to-receive-a-model-bus-reference-from-a-dsl-in-a-target-dsl-or-uml-project"></a>Pro příjem odkaz sběrnice modelu z DSL v projektu cíl DSL nebo UML

1.  V projektu DSL cíl přidejte odkazy na projekt na:

    -   Zdroj Dsl projektu.

    -   Zdroj ModelBus projektu.

2.  V souboru kódu gesto obslužná rutina přidejte následující odkazy na obor názvů:

    ```csharp
    using Microsoft.VisualStudio.Modeling;
    using Microsoft.VisualStudio.Modeling.ExtensionEnablement;
    using Microsoft.VisualStudio.Modeling.Diagrams;
    using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;
    using Microsoft.VisualStudio.Modeling.Integration;
    using SourceDslNamespace;
    using SourceDslNamespace.ModelBusAdapters;

    ```

3.  Následující příklad ukazuje, jak získat přístup k modelu element source:

    ```
    partial class MyTargetShape // or diagram or connector
    {
      internal void ProcessDragDropItem(DiagramDragEventArgs diagramDragEventArgs)
      {
        // Verify that we're being passed an Object Shape.
        ElementGroupPrototype prototype = diagramDragEventArgs.Prototype;
        if (prototype == null) return;
        if (Company.InstanceDiagrams.ObjectShape.DomainClassId
          != prototype.RootProtoElements.First().DomainClassId)
          return;
        // - This is an ObjectShape.
        // - We need to access the originating Store, find the shape, and get its object.

        IModelBus modelBus = targetDropElement.Store.GetService(typeof(SModelBus)) as IModelBus;

        // Unpack the MBR that was packed in Copy:
        ModelBusReference reference = diagramDragEventArgs.Data.GetData("ModelBusReference") as ModelBusReference;
        using (SourceDslAdapter adapter = modelBus.CreateAdapter(reference) as SourceDslAdapter)
        {
          using (ILinkedUndoTransaction t = LinkedUndoContext.BeginTransaction("doing things"))
          {
            // Quickest way to get the shape from the MBR:
            ObjectShape firstShape = adapter.ResolveElementReference<ObjectShape>(reference);

            // But actually there might be several shapes - so get them from the prototype instead:
            IElementDirectory remoteDirectory = adapter.Store.ElementDirectory;
            foreach (Guid shapeGuid in prototype.SourceRootElementIds)
            {
              PresentationElement pe = remoteDirectory.FindElement(shapeGuid) as PresentationElement;
              if (pe == null) continue;
              SourceElement instance = pe.ModelElement as SourceElement;
              if (instance == null) continue;

              // Do something with the object:
          instance...
            }
            t.Commit();
          }
        }
    }

    ```

### <a name="to-accept-an-element-sourced-from-a-uml-model"></a>Tak, aby přijímal element Source z modelu UML

-   Následující ukázka kódu přijímá objekt z diagramu UML.

    ```csharp

      using Microsoft.VisualStudio.ArchitectureTools.Extensibility;
      using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;
      using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;
      using Microsoft.VisualStudio.Modeling;
      using Microsoft.VisualStudio.Modeling.Diagrams;
      using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;
      using Microsoft.VisualStudio.Uml.Classes;
      using System;
      using System.ComponentModel.Composition;
      using System.Linq;
    ...
    partial class TargetShape
    {
      internal void ProcessDragDropItem(DiagramDragEventArgs diagramDragEventArgs)
      {
            EnvDTE.DTE dte = this.Store.GetService(typeof(EnvDTE.DTE)) as EnvDTE.DTE;
            // Find the UML project
            foreach (EnvDTE.Project project in dte.Solution.Projects)
            {
              IModelingProject modelingProject = project as IModelingProject;
              if (modelingProject == null) continue; // not a modeling project
              IModelStore store = modelingProject.Store;
              if (store == null) return;

              foreach (IDiagram dd in store.Diagrams())
              {
                  // Get Modeling.Diagram that implements UML.IDiagram:
                  Diagram diagram = dd.GetObject<Diagram>();

                  foreach (Guid elementId in e.Prototype.SourceRootElementIds)
                  {
                    ShapeElement shape = diagram.Partition.ElementDirectory.FindElement(elementId) as ShapeElement;
                    if (shape == null) continue;
                    // This example assumes the shape is a UML class:
                    IClass classElement = shape.ModelElement as IClass;
                    if (classElement == null) continue;

                    // Now do something with the UML class element ...
                  }
            }
          break; // don't try any more projects
    }  }  }

    ```

##  <a name="mouseActions"></a> Pomocí akce myši: Přetáhnete položky prostředí
 Můžete napsat obslužnou rutinu, která zabrání akce myši na pole obrazce. Následující příklad umožňuje uživateli změnit pořadí položek v prostoru přetažením pomocí myši.

 Pokud chcete vytvořit tento příklad, vytvořte pomocí řešení **diagramů tříd** šablona řešení. Přidání souboru kódu a přidejte následující kód. Upravte obor názvů být stejný jako vlastní.

```csharp
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Design;
using Microsoft.VisualStudio.Modeling.Diagrams;
using System.Collections.Generic;
using System.Linq;

// This sample allows users to re-order items in a compartment shape by dragging.

// This example is built on the "Class Diagrams" solution template of VMSDK (DSL Tools).
// You will need to change the following domain class names to your own:
// ClassShape = a compartment shape
// ClassModelElement = the domain class displayed using a ClassShape
// This code assumes that the embedding relationships displayed in the compartments
// don't use inheritance (don't have base or derived domain relationships).

namespace Company.CompartmentDrag  // EDIT.
{
 /// <summary>
 /// Manage the mouse while dragging a compartment item.
 /// </summary>
 public class CompartmentDragMouseAction : MouseAction
 {
  private ModelElement sourceChild;
  private ClassShape sourceShape;
  private RectangleD sourceCompartmentBounds;

  public CompartmentDragMouseAction(ModelElement sourceChildElement, ClassShape sourceParentShape, RectangleD bounds)
   : base (sourceParentShape.Diagram)
  {
   sourceChild = sourceChildElement;
   sourceShape = sourceParentShape;
   sourceCompartmentBounds = bounds; // For cursor.
  }

  /// <summary>
  /// Call back to the source shape to drop the dragged item.
  /// </summary>
  /// <param name="e"></param>
  protected override void OnMouseUp(DiagramMouseEventArgs e)
  {
   base.OnMouseUp(e);
   sourceShape.DoMouseUp(sourceChild, e);
   this.Cancel(e.DiagramClientView);
   e.Handled = true;
  }

  /// <summary>
  /// Ideally, this shouldn't happen. This action should only be active
  /// while the mouse is still pressed. However, it can happen if you
  /// move the mouse rapidly out of the source shape, let go, and then
  /// click somewhere else in the source shape. Yuk.
  /// </summary>
  /// <param name="e"></param>
  protected override void OnMouseDown(DiagramMouseEventArgs e)
  {
   base.OnMouseDown(e);
   this.Cancel(e.DiagramClientView);
   e.Handled = false;
  }

  /// <summary>
  /// Display an appropriate cursor while the drag is in progress:
  /// Up-down arrow if we are inside the original compartment.
  /// No entry if we are elsewhere.
  /// </summary>
  /// <param name="currentCursor"></param>
  /// <param name="diagramClientView"></param>
  /// <param name="mousePosition"></param>
  /// <returns></returns>
  public override System.Windows.Forms.Cursor GetCursor(System.Windows.Forms.Cursor currentCursor, DiagramClientView diagramClientView, PointD mousePosition)
  {
   // If the cursor is inside the original compartment, show up-down cursor.
   return sourceCompartmentBounds.Contains(mousePosition)
    ? System.Windows.Forms.Cursors.SizeNS // Up-down arrow.
    : System.Windows.Forms.Cursors.No;
  }
 }

 /// <summary>
 /// Override some methods of the compartment shape.
 /// *** GenerateDoubleDerived must be set for this shape in DslDefinition.dsl. ****
 /// </summary>
 public partial class ClassShape
 {
  /// <summary>
  /// Model element that is being dragged.
  /// </summary>
  private static ClassModelElement dragStartElement = null;
  /// <summary>
  /// Absolute bounds of the compartment, used to set the cursor.
  /// </summary>
  private static RectangleD compartmentBounds;

  /// <summary>
  /// Attach mouse listeners to the compartments for the shape.
  /// This is called once per compartment shape.
  /// The base method creates the compartments for this shape.
  /// </summary>
  public override void EnsureCompartments()
  {
   base.EnsureCompartments();
   foreach (Compartment compartment in this.NestedChildShapes.OfType<Compartment>())
   {
    compartment.MouseDown += new DiagramMouseEventHandler(compartment_MouseDown);
    compartment.MouseUp += new DiagramMouseEventHandler(compartment_MouseUp);
    compartment.MouseMove += new DiagramMouseEventHandler(compartment_MouseMove);
   }
  }

  /// <summary>
  /// Remember which item the mouse was dragged from.
  /// We don't create an Action immediately, as this would inhibit the
  /// inline text editing feature. Instead, we just remember the details
  /// and will create an Action when/if the mouse moves off this list item.
  /// </summary>
  /// <param name="sender"></param>
  /// <param name="e"></param>
  void compartment_MouseDown(object sender, DiagramMouseEventArgs e)
  {
   dragStartElement = e.HitDiagramItem.RepresentedElements.OfType<ClassModelElement>().FirstOrDefault();
   compartmentBounds = e.HitDiagramItem.Shape.AbsoluteBoundingBox;
  }

  /// <summary>
  /// When the mouse moves away from the initial list item, but still inside the compartment,
  /// create an Action to supervise the cursor and handle subsequent mouse events.
  /// Transfer the details of the initial mouse position to the Action.
  /// </summary>
  /// <param name="sender"></param>
  /// <param name="e"></param>
  void compartment_MouseMove(object sender, DiagramMouseEventArgs e)
  {
   if (dragStartElement != null)
   {
    if (dragStartElement != e.HitDiagramItem.RepresentedElements.OfType<ClassModelElement>().FirstOrDefault())
    {
     e.DiagramClientView.ActiveMouseAction = new CompartmentDragMouseAction(dragStartElement, this, compartmentBounds);
     dragStartElement = null;
    }
   }
  }

  /// <summary>
  /// User has released the mouse button.
  /// </summary>
  /// <param name="sender"></param>
  /// <param name="e"></param>
  void compartment_MouseUp(object sender, DiagramMouseEventArgs e)
  {
    dragStartElement = null;
  }

  /// <summary>
  /// Forget the source item if mouse up occurs outside the
  /// compartment.
  /// </summary>
  /// <param name="e"></param>
  public override void OnMouseUp(DiagramMouseEventArgs e)
  {
   base.OnMouseUp(e);
   dragStartElement = null;
  }

  /// <summary>
  /// Called by the Action when the user releases the mouse.
  /// If we are still on the same compartment but in a different list item,
  /// move the starting item to the position of the current one.
  /// </summary>
  /// <param name="dragFrom"></param>
  /// <param name="e"></param>
  public void DoMouseUp(ModelElement dragFrom, DiagramMouseEventArgs e)
  {
   // Original or "from" item:
   ClassModelElement dragFromElement = dragFrom as ClassModelElement;
   // Current or "to" item:
   ClassModelElement dragToElement = e.HitDiagramItem.RepresentedElements.OfType<ClassModelElement>().FirstOrDefault();
   if (dragFromElement != null && dragToElement != null)
   {
    // Find the common parent model element, and the relationship links:
    ElementLink parentToLink = GetEmbeddingLink(dragToElement);
    ElementLink parentFromLink = GetEmbeddingLink(dragFromElement);
    if (parentToLink != parentFromLink && parentFromLink != null && parentToLink != null)
    {
     // Get the static relationship and role (= end of relationship):
     DomainRelationshipInfo relationshipFrom = parentFromLink.GetDomainRelationship();
     DomainRoleInfo parentFromRole = relationshipFrom.DomainRoles[0];
     // Get the node in which the element is embedded, usually the element displayed in the shape:
     ModelElement parentFrom = parentFromLink.LinkedElements[0];

     // Same again for the target:
     DomainRelationshipInfo relationshipTo = parentToLink.GetDomainRelationship();
     DomainRoleInfo parentToRole = relationshipTo.DomainRoles[0];
     ModelElement parentTo = parentToLink.LinkedElements[0];

     // Mouse went down and up in same parent and same compartment:
     if (parentTo == parentFrom && relationshipTo == relationshipFrom)
     {
      // Find index of target position:
      int newIndex = 0;
      var elementLinks = parentToRole.GetElementLinks(parentTo);
      foreach (ElementLink link in elementLinks)
      {
       if (link == parentToLink) { break; }
       newIndex++;
      }

      if (newIndex < elementLinks.Count)
      {
       using (Transaction t = parentFrom.Store.TransactionManager.BeginTransaction("Move list item"))
       {
        parentFromLink.MoveToIndex(parentFromRole, newIndex);
        t.Commit();
       }
      }
     }
    }
   }
  }

  /// <summary>
  /// Get the embedding link to this element.
  /// Assumes there is no inheritance between embedding relationships.
  /// (If there is, you need to make sure you've got the relationship
  /// that is represented in the shape compartment.)
  /// </summary>
  /// <param name="child"></param>
  /// <returns></returns>
  ElementLink GetEmbeddingLink(ClassModelElement child)
  {
   foreach (DomainRoleInfo role in child.GetDomainClass().AllEmbeddedByDomainRoles)
   {
    foreach (ElementLink link in role.OppositeDomainRole.GetElementLinks(child))
    {
     // Just the assume the first embedding link is the only one.
     // Not a valid assumption if one relationship is derived from another.
     return link;
    }
   }
   return null;
  }
 }
}

```

## <a name="see-also"></a>Viz také

- [Přizpůsobení chování kopírování](../modeling/customizing-copy-behavior.md)
- [Nasazení řešení jazyka specifického pro doménu](../modeling/deploying-domain-specific-language-solutions.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]