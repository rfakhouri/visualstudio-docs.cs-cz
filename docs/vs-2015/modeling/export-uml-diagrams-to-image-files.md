---
title: Export diagramů UML do souborů obrázků | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: b29ce2a5-0ee3-4ab7-9aa3-13ca9c6b37a2
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 782d5da27898de7a332824e6fb07842710ab0656
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68871843"
---
# <a name="export-uml-diagrams-to-image-files"></a>Export diagramů UML do souborů obrázků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dokument UML můžete exportovat z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] aplikace do obrázku, který je pod ovládacím prvkem program. Můžete to třeba udělat jako součást automatického generování dokumentů.

 Pokud chcete dokument exportovat do obrázku ručně, můžete kopírovat a vkládat tvary z diagramu do jiných programů, jako je například Word. Dokumenty můžete také tisknout do formátu XPS. Další informace najdete v tématu [Export diagramů jako obrázků](../modeling/export-diagrams-as-images.md).

## <a name="saving-an-image"></a>Uložení obrázku
 Následující kód definuje příkaz místní nabídky, označovaný také jako příkaz místní nabídky, který ukládá obrázek do souboru.

> [!NOTE]
> Chcete-li, aby tento kód pracoval jako příkaz nabídky, je nutné jej začlenit do komponenty MEF. Další informace najdete v tématu [Definování příkazu nabídky v diagramu modelování](../modeling/define-a-menu-command-on-a-modeling-diagram.md).

 Kód nejprve používá [IShape. GetObject](/previous-versions/ee789371(v=vs.140)) k získání <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram> základní implementace. Tento typ obsahuje metodu <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.CreateBitmap%2A>.

```
namespace SaveToImage
{
  using System.ComponentModel.Composition; // for [Import], [Export]
  using System.Drawing; // for Bitmap
  using System.Drawing.Imaging; // for ImageFormat
  using System.Linq; // for collection extensions
  using System.Windows.Forms; // for SaveFileDialog
  using Microsoft.VisualStudio.Modeling.Diagrams;
    // for Diagram
  using Microsoft.VisualStudio.Modeling.ExtensionEnablement;
    // for IGestureExtension, ICommandExtension, ILinkedUndoContext
  using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;
    // for IDiagramContext
  using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;
    // for designer extension attributes

  /// <summary>
  /// Called when the user clicks the menu item.
  /// </summary>
  // Context menu command applicable to any UML diagram
  [Export(typeof(ICommandExtension))]
  [ClassDesignerExtension]
  [UseCaseDesignerExtension]
  [SequenceDesignerExtension]
  [ComponentDesignerExtension]
  [ActivityDesignerExtension]
  class CommandExtension : ICommandExtension
  {
    [Import]
    IDiagramContext Context { get; set; }

    public void Execute(IMenuCommand command)
    {
      // Get the diagram of the underlying implementation.
      Diagram dslDiagram = Context.CurrentDiagram.GetObject<Diagram>();
      if (dslDiagram != null)
      {
        string imageFileName = FileNameFromUser();
        if (!string.IsNullOrEmpty(imageFileName))
        {
          Bitmap bitmap = dslDiagram.CreateBitmap(
           dslDiagram.NestedChildShapes,
           Diagram.CreateBitmapPreference.FavorClarityOverSmallSize);
          bitmap.Save(imageFileName, GetImageType(imageFileName));
        }
      }
    }

    /// <summary>
    /// Called when the user right-clicks the diagram.
    /// Set Enabled and Visible to specify the menu item status.
    /// </summary>
    /// <param name="command"></param>
    public void QueryStatus(IMenuCommand command)
    {
      command.Enabled = Context.CurrentDiagram != null
        && Context.CurrentDiagram.ChildShapes.Count() > 0;
    }

    /// <summary>
    /// Menu text.
    /// </summary>
    public string Text
    {
      get { return "Save To Image..."; }
    }

    /// <summary>
    /// Ask the user for the path of an image file.
    /// </summary>
    /// <returns>image file path, or null</returns>
    private string FileNameFromUser()
    {
      SaveFileDialog dialog = new SaveFileDialog();
      dialog.AddExtension = true;
      dialog.DefaultExt = "image.bmp";
      dialog.Filter = "Bitmap ( *.bmp )|*.bmp|JPEG File ( *.jpg )|*.jpg|Enhanced Metafile (*.emf )|*.emf|Portable Network Graphic ( *.png )|*.png";
      dialog.FilterIndex = 1;
      dialog.Title = "Save Diagram to Image";
      return dialog.ShowDialog() == DialogResult.OK ? dialog.FileName : null;
    }

    /// <summary>
    /// Return the appropriate image type for a file extension.
    /// </summary>
    /// <param name="fileName"></param>
    /// <returns></returns>
    private ImageFormat GetImageType(string fileName)
    {
      string extension = System.IO.Path.GetExtension(fileName).ToLowerInvariant();
      ImageFormat result = ImageFormat.Bmp;
      switch (extension)
      {
        case ".jpg":
          result = ImageFormat.Jpeg;
          break;
        case ".emf":
          result = ImageFormat.Emf;
          break;
        case ".png":
          result = ImageFormat.Png;
          break;
      }
      return result;
    }
  }
}
```

## <a name="see-also"></a>Viz také
 [Exportovat diagramy jako obrázky](../modeling/export-diagrams-as-images.md) [Definování příkazu nabídky v diagramu modelování](../modeling/define-a-menu-command-on-a-modeling-diagram.md)
