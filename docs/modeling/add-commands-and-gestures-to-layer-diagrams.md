---
title: Přidání příkazů a gest do diagramů závislostí
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom commands
- dependency diagrams, adding custom gestures
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 880e50f2b9d16886dddb0248fadc905ec0492595
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="add-commands-and-gestures-to-dependency-diagrams"></a>Přidání příkazů a gest do diagramů závislostí
Můžete definovat příkazy nabídky kontextu a gesty obslužné rutiny v diagramech závislosti v sadě Visual Studio. Tato rozšíření můžete balíček do Visual Studio integrace rozšíření (VSIX), které můžete distribuovat jiným uživatelům v sadě Visual Studio.

 Pokud chcete, můžete definovat několik obslužné rutiny příkazů a gesto ve stejném projektu sady Visual Studio. Můžete také kombinovat několik těchto projektů do jednoho VSIX. Můžete třeba definovat jeden VSIX, který obsahuje příkazy pro vrstvy a jazyk specifické pro doménu.

> [!NOTE]
>  Můžete také upravit Architektura ověření uživatele, jejichž zdroje kód je ve srovnání s diagramy závislostí. Architektura ověření byste měli definovat v samostatném projektu sady Visual Studio. Můžete ho přidat do stejné VSIX jako ostatní rozšíření. Další informace najdete v tématu [přidání ověřování vlastní architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md).

## <a name="requirements"></a>Požadavky
 V tématu [požadavky](../modeling/extend-layer-diagrams.md#prereqs).

## <a name="defining-a-command-or-gesture-in-a-new-vsix"></a>Definování příkazu nebo gesto v nové VSIX
 Nejrychlejší způsob vytváření rozšíření je pro použití šablony projektu. Tento kód a VSIX manifest umístí do stejného projektu.

#### <a name="to-define-an-extension-by-using-a-project-template"></a>Můžete definovat rozšíření pomocí šablony projektu

1.  Vytvoření projektu v nové řešení pomocí **nový projekt** příkaz na **souboru** nabídky.

2.  V **nový projekt** dialogovém **projekty modelování**, vyberte buď **rozšíření příkaz Návrhář vrstev** nebo **rozšíření gesto Návrhář vrstev** .

     Vytvoří šablona dílčí projekt, který obsahuje malé příklad práci.

3.  Chcete-li otestovat rozšíření, stiskněte **CTRL + F5** nebo **F5**.

     Spustí experimentální instanci sady Visual Studio. V tomto případě vytvořte diagram závislostí. Příkaz nebo gesto rozšíření by měla fungovat v tomto diagramu.

4.  Ukončete experimentální instanci a upravte ukázkový kód. Další informace najdete v tématu [vyhledání a aktualizace modelů v programovém kódu vrstvy](../modeling/navigate-and-update-layer-models-in-program-code.md).

5.  Další příkaz nebo gesto obslužné rutiny můžete přidat do stejné projektu. Další informace najdete v jednom z následujících částí:

     [Definování příkazu nabídky](#command)

     [Definování obslužné rutiny gest](#gesture)

6.  Chcete-li nainstalovat rozšíření v hlavní instanci sady Visual Studio, nebo v jiném počítači, vyhledejte **VSIX** souboru v **bin\\\***. Zkopírujte jej do počítače, ve které chcete nainstalovat a pak na ni dvakrát kliknete. Chcete-li ho odinstalovat, použijte **rozšíření a aktualizace** na **nástroje** nabídky.

## <a name="adding-a-command-or-gesture-to-a-separate-vsix"></a>Přidání příkaz nebo gesto do samostatné VSIX
 Pokud chcete vytvořit jednu VSIX, který obsahuje příkazy, validátory vrstvy a ostatní rozšíření, doporučujeme vytvořit jeden projekt k definování VSIX a samostatné projekty pro obslužné rutiny.

#### <a name="to-add-layer-extensions-to-a-separate-vsix"></a>Přidání rozšíření vrstvy do samostatné VSIX

1.  Vytvoření projektu knihovny tříd do nového nebo existujícího řešení sady Visual Studio. V **nový projekt** dialogové okno, klikněte na tlačítko **Visual C#** a pak klikněte na **knihovny tříd**. Tento projekt bude obsahovat příkaz nebo gesty třídy obslužné rutiny.

    > [!NOTE]
    >  Můžete definovat více než jeden příkaz nebo gesto třídu obslužné rutiny v knihovně tříd, ale byste měli definovat třídy ověření vrstvy v knihovně samostatné třídy.

2.  Identifikovat nebo vytvoření projektu VSIX ve vašem řešení. VSIX projekt obsahuje soubor s názvem **source.extension.vsixmanifest**. Chcete-li přidat VSIX projektu:

    1.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#**, pak klikněte na tlačítko **rozšiřitelnost**a potom klikněte na **projektu VSIX**.

    2.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt VSIX a pak klikněte na tlačítko **nastavit jako spouštěný projekt**.

    3.  Klikněte na tlačítko **vyberte edice** a ujistěte se, že **Visual Studio** je zaškrtnuté.

3.  V **source.extension.vsixmanifest**v části **prostředky**, přidejte příkaz nebo gesty obslužná rutina projektu jako součást MEF.

    1.  V **prostředky**TAB, zvolte **nový**.

    2.  V **typ**, vyberte **Microsoft.VisualStudio.MefComponent**.

    3.  V **zdroj**, vyberte **projekt v aktuálním řešení** a vyberte název projektu příkaz nebo gesto obslužné rutiny.

    4.  Uložte soubor.

4.  Vraťte se na projektu obslužná rutina příkazu nebo gesto a přidejte následující odkazy na projekt.

|**Referenční informace**|**Co můžete udělat**|
|-------------------|------------------------------------|
|Program Files\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.dll|Vytvářet a upravovat vrstev.|
|Microsoft.VisualStudio.Uml.Interfaces|Vytvářet a upravovat vrstev.|
|Microsoft.VisualStudio.ArchitectureTools.Extensibility|Upravit obrazce v diagramech|
|System.ComponentModel.Composition|Definování komponent pomocí Managed Extensibility Framework (MEF)|
|Microsoft.VisualStudio.Modeling.Sdk.[version]|Definujte rozšíření modelování|
|Microsoft.VisualStudio.Modeling.Sdk.Diagrams.[version]|Aktualizace tvarů a diagramy|

1.  Upravte soubor – třída v C# projektu knihovny tříd obsahuje kód pro rozšíření. Další informace najdete v jednom z následujících částí:

     [Definování příkazu nabídky](#command)

     [Definování obslužné rutiny gest](#gesture)

     Viz také [vyhledání a aktualizace modelů v programovém kódu vrstvy](../modeling/navigate-and-update-layer-models-in-program-code.md).

2.  Chcete-li otestovat funkci, stiskněte CTRL + F5 nebo F5. Otevře se experimentální instanci sady Visual Studio. V tomto případě vytvořit nebo Otevřít diagram závislostí.

3.  Chcete-li nainstalovat VSIX hlavní instanci sady Visual Studio, nebo na jiném počítači, vyhledejte **VSIX** souboru v **bin** adresář projektu VSIX. Zkopírujte jej do počítače, ve které chcete nainstalovat VSIX. Poklikejte na soubor VSIX v Průzkumníku Windows.

     Chcete-li ho odinstalovat, použijte **rozšíření a aktualizace** na **nástroje** nabídky.

##  <a name="command"></a> Definování příkazu nabídky
 Další definice příkaz nabídky můžete přidat do existující gesto nebo příkaz projektu. Každý příkaz je definováno třídu, která má následující vlastnosti:

-   Třída je deklarovaná následujícím způsobem:

     `[LayerDesignerExtension]`

     `[Export(typeof(ICommandExtension))]`

     `public class`  *MyLayerCommand*  `: ICommandExtension { ... }`

-   Obor názvů a název třídy jsou důležitý.

-   Metody, které implementují `ICommandExtension` jsou následující:

    -   `string Text {get;}` -Štítek, který se zobrazí v nabídce.

    -   `void QueryStatus(IMenuCommand command)` -volána, když uživatel klikne na diagramu pravým tlačítkem myši a určuje, zda příkaz by měla být viditelné a povolené pro aktuální výběr uživatele.

    -   `void Execute(IMenuCommand command)` -volána, když uživatel vybere příkaz.

-   Pokud chcete zjistit aktuální výběr, můžete importovat `IDiagramContext`:

     `[Import]`

     `public IDiagramContext DiagramContext { get; set; }`

     `...`

     `DiagramContext.CurrentDiagram.SelectedShapes.Count()...`

 Další informace najdete v tématu [vyhledání a aktualizace modelů v programovém kódu vrstvy](../modeling/navigate-and-update-layer-models-in-program-code.md).

 Pokud chcete přidat nový příkaz, vytvořte nový soubor kód, který obsahuje následující ukázka. Potom otestovat a upravit ho.

```
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;
using System.ComponentModel.Composition;
using System.Linq;

namespace MyLayerExtension // Change to your preference.
{
  // This is a feature for dependency diagrams:
  [LayerDesignerExtension]
  // This feature is a menu command:
  [Export(typeof(ICommandExtension))]
  // Change the class name to your preference:
  public class MyLayerCommand : ICommandExtension
  {
    [Import]
    public IDiagramContext DiagramContext { get; set; }

    [Import]
    public ILinkedUndoContext LinkedUndoContext { get; set; }

    // Menu command label:
    public string Text
    {
      get { return "Duplicate layers"; }
    }

    // Called when the user right-clicks the diagram.
    // Defines whether the command is visible and enabled.
    public void QueryStatus(IMenuCommand command)
    {
      command.Visible =
      command.Enabled = DiagramContext.CurrentDiagram
        .SelectedShapes.Count() > 0;
    }

    // Called when the user selects the command.
    public void Execute(IMenuCommand command)
    {
      // A selection of starting points:
      IDiagram diagram = this.DiagramContext.CurrentDiagram;
      ILayerModel lmodel = diagram.GetLayerModel();
      foreach (ILayer layer in lmodel.Layers)
      { // All layers in model.
      }
      // Updates should be performed in a transaction:
      using (ILinkedUndoTransaction t =
        LinkedUndoContext.BeginTransaction("copy selection"))
      {
        foreach (ILayer layer in
          diagram.SelectedShapes
            .Select(shape=>shape.GetLayerElement())
            .Where(element => element is ILayer))
        {
          ILayer copy = lmodel.CreateLayer(layer.Name + "+");
          // Position the shapes:
          IShape originalShape = layer.GetShape();
          copy.GetShape().Move(
            originalShape.XPosition + originalShape.Width * 1.2,
            originalShape.YPosition);
        }
        t.Commit();
      }
    }
  }
}
```

##  <a name="gesture"></a> Definování obslužné rutiny gest
 Obslužné rutiny gest odpoví, když uživatel nastavuje tažením položky do diagramu závislostí a při poklepání kdekoli v diagramu.

 Chcete existující příkaz nebo gesto obslužná rutina VSIX projektu můžete přidat soubor kód, který definuje obslužné rutiny gest:

```
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;
using System.ComponentModel.Composition;
using System.Linq;
namespace MyLayerExtensions // change to your preference
{
  [LayerDesignerExtension]
  [Export(typeof(IGestureExtension))]
  public class MyLayerGestureHandler : IGestureExtension
  {
  }
}
```

 Všimněte si následujících bodů o gesto obslužné rutiny:

-   Členové `IGestureExtension` jsou následující:

     **OnDoubleClick** -volána při poklepání kdekoli v diagramu.

     **CanDragDrop** – volané opakovaně jako uživatel přesune myši při přetažení položky do diagramu. Rychle musí fungovat.

     **OnDragDrop** -volána, když se uživatel přesune položku do diagramu.

-   První argument pro každou metodu je `IShape`, ze kterého můžete získat element vrstvy. Příklad:

    ```
    public void OnDragDrop(IShape target, IDataObject data)
    {
        ILayerElement element = target.GetLayerElement();
        if (element is ILayer)
        {
            // ...
        }
    }
    ```

-   Obslužné rutiny pro některé typy taženou položku je již definován. Například můžete uživatele přetáhnout položky v Průzkumníku řešení na diagram závislostí. Nelze definovat přetáhněte obslužnou rutinu pro tyto typy položky. V těchto případech vaší `DragDrop` uplatněny metody.


## <a name="see-also"></a>Viz také

- [Procházení a aktualizace modelů vrstev v programovém kódu](../modeling/navigate-and-update-layer-models-in-program-code.md)
- [Přidání vlastního ověřování architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)
