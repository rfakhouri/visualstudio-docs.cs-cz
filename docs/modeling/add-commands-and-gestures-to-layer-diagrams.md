---
title: Přidávání příkazů a gest do diagramů závislostí
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom commands
- dependency diagrams, adding custom gestures
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce8bc44bf506cf315420aad4108832f7461f1c70
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60077872"
---
# <a name="add-commands-and-gestures-to-dependency-diagrams"></a>Přidávání příkazů a gest do diagramů závislostí

Můžete definovat příkazy nabídky klikněte pravým tlačítkem a obslužné rutiny gesta v diagramech závislostí v sadě Visual Studio. Tato rozšíření můžete zabalit do Visual Studio integrace rozšíření (VSIX), které můžete distribuovat ostatním uživatelům aplikace Visual Studio.

Pokud chcete, můžete definovat několik obslužných rutin příkazů a gest ve stejném projektu sady Visual Studio. Můžete také kombinovat několik takových projektů do jednoho souboru VSIX. Můžete například definovat jeden VSIX obsahující příkazy vrstvy a jazyka specifického pro doménu.

> [!NOTE]
> Můžete také přizpůsobit ověřování architektury, ve které uživatelé zdroji kód je ve srovnání s diagramy závislostí. Architektura ověření by měl definovat v samostatném projektu sady Visual Studio. Můžete ho přidat do stejného VSIX jako další rozšíření. Další informace najdete v tématu [přidání ověřování vlastní architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md).

## <a name="requirements"></a>Požadavky

Zobrazit [požadavky](../modeling/extend-layer-diagrams.md#prereqs).

## <a name="define-a-command-or-gesture-in-a-new-vsix"></a>Definování příkazu nebo gesta v novém souboru VSIX

Nejrychlejší způsob vytváření rozšíření je použití šablony projektu. To umístí kód a VSIX manifest do stejného projektu.

1. Vytvořte nový **rozšíření příkazu návrháře vrstvy** nebo **vrstva rozšíření gesta návrháře** projektu.

   Šablona vytvoří projekt, který obsahuje malý funkční příklad.

2. Chcete-li otestovat rozšíření, stiskněte **Ctrl**+**F5** nebo **F5**.

    Spustí se experimentální instanci sady Visual Studio. V takovém případě vytvořte diagram závislostí. Vaše rozšíření příkazu nebo gesta by měla fungovat v tomto diagramu.

3. Ukončete experimentální instanci a úprava vzorového kódu.

4. Můžete přidat další obslužné rutiny příkazu nebo gesta do stejného projektu. Další informace naleznete v následující části:

    [Definování příkazu nabídky](#command)

    [Definování obslužné rutiny gesta](#gesture)

::: moniker range="vs-2017"

5. Chcete-li nainstalovat rozšíření v instanci hlavní aplikace Visual Studio nebo na jiném počítači, vyhledejte *VSIX* ve *bin* adresáře. Zkopírujte ho do počítače, ve které chcete nainstalovat a poklepejte na něj. Chcete-li ho odinstalovat, zvolte **rozšíření a aktualizace** na **nástroje** nabídky.

::: moniker-end

::: moniker range=">=vs-2019"

5. Chcete-li nainstalovat rozšíření v instanci hlavní aplikace Visual Studio nebo na jiném počítači, vyhledejte *VSIX* ve *bin* adresáře. Zkopírujte ho do počítače, ve které chcete nainstalovat a poklepejte na něj. Chcete-li ho odinstalovat, zvolte **spravovat rozšíření** na **rozšíření** nabídky.

::: moniker-end

## <a name="add-a-command-or-gesture-to-a-separate-vsix"></a>Přidání příkazu nebo gesta do samostatného souboru VSIX

Pokud chcete vytvořit jeden VSIX, který obsahuje příkazy, validátory vrstvy a další rozšíření, doporučujeme vytvořit jeden projekt k definování VSIX a samostatné projekty pro obslužné rutiny.

1. Vytvořte nový **knihovny tříd** projektu. Tento projekt bude obsahovat příkaz nebo třídy obslužné rutiny gesta.

   > [!NOTE]
   > Můžete definovat více než jednu třídu obslužné rutiny příkazu nebo gesta v jedné knihovně tříd, ale měli byste definovat třídy ověřování vrstvy v samostatné knihovně tříd.

2. Přidejte nebo vytvořte VSIX projekt ve vašem řešení. Projekt VSIX obsahuje soubor s názvem **source.extension.vsixmanifest**.

3. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt VSIX a zvolte **nastavit jako spouštěný projekt**.

4. V **source.extension.vsixmanifest**v části **prostředky**, přidání příkazu nebo gesta projektu obslužné rutiny jako komponentu MEF.

    1. V **prostředky**TAB, zvolte **nový**.

    2. Na **typ**vyberte **Microsoft.VisualStudio.MefComponent**.

    3. Na **zdroj**vyberte **projekt v aktuálním řešení** a vyberte název projektu obslužné rutiny příkazu nebo gesta.

    4. Uložte soubor.

5. Vraťte se do projektu obslužné rutiny příkazu nebo gesta a přidejte následující odkazy projektu:

   |**Referenční informace**|**To umožňuje provést**|
   |-|-|
   |Program Files\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.dll|Vytvořit a upravit vrstvy|
   |Microsoft.VisualStudio.Uml.Interfaces|Vytvořit a upravit vrstvy|
   |Microsoft.VisualStudio.ArchitectureTools.Extensibility|Upravit tvary v diagramech|
   |System.ComponentModel.Composition|Definovat součásti pomocí Managed Extensibility Framework (MEF)|
   |Microsoft.VisualStudio.Modeling.Sdk.[version]|Definovat rozšíření modelování|
   |Microsoft.VisualStudio.Modeling.Sdk.Diagrams.[version]|Aktualizovat tvary a diagramy|

6. Upravte soubor třídy v jazyce C# projekt knihovny tříd obsahující kód pro rozšíření. Další informace naleznete v následující části:

     [Definování příkazu nabídky](#command)

     [Definování obslužné rutiny gesta](#gesture)

7. Chcete-li otestovat funkci, stiskněte **Ctrl**+**F5** nebo **F5**.

   Otevře se experimentální instanci sady Visual Studio. V takovém případě vytvořte nebo otevřete diagram závislostí.

8. Chcete-li nainstalovat VSIX v instanci hlavní aplikace Visual Studio nebo na jiném počítači, vyhledejte **VSIX** soubor **bin** adresáře projektu VSIX. Zkopírujte ho do počítače, ve které chcete nainstalovat VSIX. Poklikejte na soubor VSIX v Průzkumníku souborů.

## <a name="command"></a> Definování příkazu nabídky

K existujícímu gestu nebo projektu příkazu můžete přidat další definice příkazu nabídky. Každý příkaz je definován třídou, která má následující vlastnosti:

- Třída je deklarována následovně:

   `[LayerDesignerExtension]`

   `[Export(typeof(ICommandExtension))]`

   `public class`  *MyLayerCommand*  `: ICommandExtension { ... }`

- Obor názvů a název třídy nejsou důležité.

- Metody, které implementují `ICommandExtension` jsou následující:

  - `string Text {get;}` – Popisek, který se zobrazí v nabídce.

  - `void QueryStatus(IMenuCommand command)` – volána, když uživatel klepne pravým tlačítkem myši v diagramu a určuje, zda má být příkaz viditelný a povolený pro aktuální výběr uživatele.

  - `void Execute(IMenuCommand command)` – volána, když uživatel vybere příkaz.

- Chcete-li zjistit aktuální výběr, můžete importovat `IDiagramContext`:

   `[Import]`

   `public IDiagramContext DiagramContext { get; set; }`

   `...`

   `DiagramContext.CurrentDiagram.SelectedShapes.Count()...`

Chcete-li přidat nový příkaz, vytvořte nový soubor kódu, který obsahuje následující ukázku. Potom ho otestujte a upravte.

```csharp
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

## <a name="gesture"></a> Definování obslužné rutiny gesta

Obslužná rutina gesta reaguje, když uživatel přetáhne položky do diagramu závislosti, a když uživatel poklepe kdekoli v diagramu.

Do vašeho existujícího příkazu nebo projektu VSIX obslužné rutiny gesta můžete přidat soubor kódu, který definuje obslužnou rutinu gesta:

```csharp
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

Všimněte si následujících o obslužných rutinách gest:

- Členové `IGestureExtension` jsou následující:

     **OnDoubleClick** – volána, když uživatel poklepe kdekoli v diagramu.

     **CanDragDrop** – voláno opakovaně, jak uživatel pohybuje ukazatelem myši při přetažení položky do diagramu. Musí pracovat rychle.

     **OnDragDrop** – volána, když uživatel zahodí položky do diagramu.

- První argument pro každou metodu je `IShape`, ze kterého můžete získat prvek vrstvy. Příklad:

    ```csharp
    public void OnDragDrop(IShape target, IDataObject data)
    {
        ILayerElement element = target.GetLayerElement();
        if (element is ILayer)
        {
            // ...
        }
    }
    ```

- Obslužné rutiny pro některé typy přetažených položek jsou již definovány. Například můžete uživateli přetáhnout položky z Průzkumníka řešení do diagram závislostí. Nelze definovat obslužnou rutinu přetažení pro tyto typy položky. V těchto případech vaše `DragDrop` metody nebudou vyvolány.

## <a name="see-also"></a>Viz také

- [Přidání vlastního ověřování architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)
