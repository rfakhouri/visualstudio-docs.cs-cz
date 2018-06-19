---
title: Procházení a aktualizace modelů vrstev v programovém kódu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- layer models, navigating in program code
- layer models, updating in program code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2be7a0fdb3204647f6874d2dceaa81eb8cac3756
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952271"
---
# <a name="navigate-and-update-layer-models-in-program-code"></a>Procházení a aktualizace modelů vrstev v programovém kódu

Tento článek popisuje elementů a vztahů v modelech vrstvy, které můžete procházení a aktualizace pomocí kódu programu. Další informace o diagramy závislost z hlediska uživatele najdete v tématu [diagramy závislost: referenční dokumentace](../modeling/layer-diagrams-reference.md) a [diagramy závislost: pokyny](../modeling/layer-diagrams-guidelines.md).

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer> Model popsaný v tomto tématu je průčelí za na další Obecné <xref:Microsoft.VisualStudio.GraphModel> modelu. Pokud píšete [příkaz nebo gesto rozšíření nabídky](../modeling/add-commands-and-gestures-to-layer-diagrams.md), použijte `Layer` modelu. Pokud píšete [vrstvy ověření rozšíření](../modeling/add-custom-architecture-validation-to-layer-diagrams.md), je jednodušší použít `GraphModel`.

## <a name="transactions"></a>Transakce

Při aktualizaci modelu, vezměte v úvahu obklopuje změny v `ILinkedUndoTransaction`, které skupiny změny do jedné transakce. Pokud se všechny změny nezdaří, je celá transakce vrácena zpět. Pokud uživatel vrátí zpět ke změně, jsou všechny změny vrátit zpět společně.

```
using (ILinkedUndoTransaction t =
        LinkedUndoContext.BeginTransaction("a name"))
{
    // Make changes here ....
    t.Commit(); // Don't forget this!
}
```

## <a name="containment"></a>Členství ve skupině

![ILayer a ILayerModel může obsahovat i ILayers.](../modeling/media/layerapi_containment.png)

Vrstvy (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayer>) a vrstva modelu (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel>) může obsahovat vrstvy a komentáře.

Vrstva (`ILayer`) může být obsažený ve model vrstvy (`ILayerModel`) nebo mohou být použity v rámci jiného `ILayer`.

Vytvoření metody vytvoření komentáře nebo vrstvy, lze používejte na příslušné kontejneru.

## <a name="dependency-links"></a>Propojení závislostí

Odkaz závislostí je reprezentována objekt. Může být navigaci v obou směrech:

![Připojí se ILayerDependencyLink dva ILayers.](../modeling/media/layerapi_dependency.png)

Chcete-li vytvořit odkaz závislostí, volejte `source.CreateDependencyLink(target)`.

## <a name="comments"></a>Komentáře

Komentáře mohou být obsaženy v vrstvy nebo model vrstvy a také může být propojený libovolný element, vrstvy:

![Komentáře lze připojit k libovolný element, vrstvy.](../modeling/media/layerapi_comments.png)

Komentář může být propojený libovolný počet elementů, včetně none.

Komentáře, které jsou připojené k element a vrstva, použijte:

```csharp
ILayerModel model = diagram.GetLayerModel();
IEnumerable<ILayerComment> comments =
   model.Comments.Where(comment =>
      comment.Links.Any(link => link.Target == layerElement));
```

> [!CAUTION]
> `Comments` Vlastnost `ILayer` získá komentáře, které jsou obsaženy v rámci `ILayer`. Komentáře, které jsou propojeny s jeho nedostane.

Vytvoření komentáře voláním `CreateComment()` na odpovídajícího kontejneru.

Vytvořit odkaz pomocí `CreateLink()` na komentář.

## <a name="layer-elements"></a>Elementy vrstvy

Všechny typy elementu, který může být obsažený v modelu jsou elementy vrstvy:

![obsah diagram závislostí je ILayerElements.](../modeling/media/layerapi_layerelements.png)

## <a name="properties"></a>Vlastnosti

Každý `ILayerElement` slovník řetězec s názvem `Properties`. Můžete připojit libovolné informace pro libovolný element, vrstvy tohoto slovníku.

## <a name="artifact-references"></a>Artefaktů odkazy

Odkaz na artefaktů (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>) představuje propojení mezi vrstvou a položka projektu, například souboru, třída nebo složky. Uživatel vytvoří artefakty při jejich vytvoření vrstvy nebo do ní přidejte tak, že přetáhnete položky z Průzkumníka řešení, zobrazení tříd nebo prohlížeč objektů na diagram závislostí. Libovolný počet artefaktů odkazy lze propojit s vrstvou.

Každý řádek v Průzkumníku vrstvy zobrazí odkaz na artefaktů. Další informace najdete v tématu [vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md).

Hlavní typy a metody nevadí artefaktů odkazy jsou následující:

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>. Vlastnost kategorií určuje, jaký druh artefaktů se odkazuje, jako jsou třídy, spustitelný soubor nebo sestavení. Kategorie vlastnost určuje, jak identifikátor identifikuje artefaktů cíl.

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ArtifactReferenceExtensions.CreateArtifactReferenceAsync%2A> Vytvoří odkaz na artefaktů z <xref:EnvDTE.Project> nebo <xref:EnvDTE.ProjectItem>. Toto je asynchronní operace. Proto obvykle nabízejí zpětného volání, která je volána po dokončení vytvoření.

Vrstvu odkazů artefaktů se liší na artefakty v diagramy případů použití.

## <a name="shapes-and-diagrams"></a>Tvarů a diagramy

Dva objekty se používají k vyjádření každý prvek ve model vrstvy: <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>a <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape>. `IShape` Představuje umístění a velikost tvaru v diagramu. V modely vrstev každých `ILayerElement` má jeden `IShape`a každou `IShape` na závislost jeden má diagram `ILayerElement`. `IShape` také se používá pro modely UML. Proto nemusí být vždy `IShape` má element vrstvy.

Stejným způsobem <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel> se zobrazí na jednom <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram>.

V kódu vlastního příkazu nebo obslužné rutiny gest, můžete získat aktuální diagram a aktuální výběr tvarů z `DiagramContext` importovat:

```
public class ... {
[Import]
    public IDiagramContext DiagramContext { get; set; }
...
public void ... (...)
{ IDiagram diagram = this.DiagramContext.CurrentDiagram;
  ILayerModel model = diagram.GetLayerModel();
  if (model != null)
  { foreach (ILayer layer in model.Layers) { ... }}
  foreach (IShape selected in diagram.SelectedShapes)
  { ILayerElement element = selected.GetLayerElement();
    if (element != null) ... }}
```

![Každý ILayerElement je předkládán IShape.](../modeling/media/layerapi_shapes.png)

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape> a <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram> se taky používají k zobrazení modely UML.

## <a name="see-also"></a>Viz také

- [Přidávání příkazů a gest do diagramů závislostí](../modeling/add-commands-and-gestures-to-layer-diagrams.md)
- [Přidání vlastního ověřování architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)
- [Přidání vlastních vlastností do diagramů závislostí](../modeling/add-custom-properties-to-layer-diagrams.md)
- [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
- [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)
