---
title: Rozšíření vašeho DSL pomocí MEF
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8cc48c70cd6fe8bd45ed65b96732d3db31a386e2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31953518"
---
# <a name="extend-your-dsl-by-using-mef"></a>Rozšíření vašeho DSL pomocí MEF
Jazyka specifické pro doménu (DSL) můžete rozšířit pomocí Managed Extensibility Framework (MEF). Vy nebo jiní vývojáři budou moci zapsat rozšíření pro DSL beze změny definice DSL a kód programu. Taková rozšíření zahrnují příkazy nabídky, obslužné rutiny přetahování myší a ověření. Budou uživatelé moci nainstalovat vaší DSL a volitelně nainstalovat rozšíření pro ni.

 Kromě toho když povolíte MEF v vaší DSL, se může být snazší pro vás bude psaní některé funkce DSL, i v případě, že všechny jsou vytvořeny společně s DSL.

 Další informace o rozhraní MEF najdete v tématu [Managed Extensibility Framework (MEF)](/dotnet/framework/mef/index).

### <a name="to-enable-your-dsl-to-be-extended-by-mef"></a>Chcete-li povolit vaší DSL potřeba rozšířit o MEF

1.  Vytvořte novou složku s názvem **MefExtension** uvnitř **DslPackage** projektu. Přidejte do ní následující soubory:

     Název souboru: `CommandExtensionVSCT.tt`

    > [!IMPORTANT]
    >  Nastavit identifikátor GUID v tomto souboru, aby byla stejná jako CommandSetId identifikátor GUID, který je definován v DslPackage\GeneratedCode\Constants.tt

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#
    // CmdSet Guid must be defined before master template is included
    // This Guid must be kept synchronized with the CommandSetId Guid in Constants.tt
    Guid guidCmdSet = new Guid ("00000000-0000-0000-0000-000000000000");
    string menuidCommandsExtensionBaseId="0x4000";
    #>
    <#@ include file="DslPackage\CommandExtensionVSCT.tt" #>
    ```

     Název souboru: `CommandExtensionRegistrar.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="DslPackage\CommandExtensionRegistrar.tt" #>
    ```

     Název souboru: `ValidationExtensionEnablement.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="DslPackage\ValidationExtensionEnablement.tt" #>
    ```

     Název souboru: `ValidationExtensionRegistrar.tt`

     Pokud chcete přidat tento soubor, musíte povolit ověření ve vašem DSL pomocí alespoň jeden z parametrů v **EditorValidation** v Průzkumníku DSL.

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="DslPackage\ValidationExtensionRegistrar.tt" #>
    ```

     Název souboru: `PackageExtensionEnablement.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="DslPackage\PackageExtensionEnablement.tt" #>
    ```

2.  Vytvořte novou složku s názvem **MefExtension** uvnitř **Dsl** projektu. Přidejte do ní následující soubory:

     Název souboru: `DesignerExtensionMetaDataAttribute.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="Dsl\DesignerExtensionMetadataAttribute.tt" #>
    ```

     Název souboru: `GestureExtensionEnablement.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="Dsl\GestureExtensionEnablement.tt" #>
    ```

     Název souboru: `GestureExtensionController.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="Dsl\GestureExtensionController.tt" #>
    ```

3.  Přidejte následující řádek na existující soubor, který je pojmenován **DslPackage\Commands.vsct**:

    ```
    <Include href="MefExtension\CommandExtensionVSCT.vsct"/>
    ```

     Vložit řádek po existující `<Include>` – direktiva.

4.  `Open DslDefinition.dsl.`

5.  V Průzkumníku DSL vyberte **Editor\Validation**.

6.  V okně Vlastnosti zkontrolujte, že nejméně jedna z vlastností s názvem **používá...**  je `true`.

7.  Na panelu nástrojů Průzkumníku řešení klikněte na tlačítko **transformaci všech šablon**.

     Podpůrné soubory se zobrazí pod všechny soubory, které jste přidali.

8.  Sestavení a spuštění řešení Chcete-li ověřit, že stále funguje.

 Vaše DSL je nyní povoleno MEF. Příkazy nabídky, obslužné rutiny gest a omezení ověřování můžete napsat jako MEF rozšíření. Můžete napsat tato rozšíření ve vašem řešení DSL společně s další vlastní kód. Kromě toho můžete nebo jinými vývojáři může zapisovat samostatné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, které rozšiřují vaše DSL.

## <a name="creating-an-extension-for-a-mef-enabled-dsl"></a>Vytváření rozšíření pro povoleným MEF DSL
 Pokud máte přístup k povoleným MEF DSL, vytvořené sobě nebo někomu jinému, můžete napsat rozšíření pro ni. Rozšíření můžete použít k přidání příkazů nabídky, obslužné rutiny gest nebo omezení ověřování. K vytváření těchto rozšíření, můžete použít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení rozšíření (VSIX). Řešení má dvě části: projektu knihovny tříd, který sestaví sestavení kódu a projekt VSIX, který balíčky sestavení.

#### <a name="to-create-a-dsl-extension-vsix"></a>Chcete-li vytvořit rozšíření DSL VSIX

1.  Vytvoření nového projektu knihovny tříd. Chcete-li to provést, v **nový projekt** dialogové okno, vyberte **jazyka Visual Basic** nebo **Visual C#** a pak vyberte **knihovny tříd**.

2.  V novém projektu knihovny tříd přidejte odkaz na sestavení DSL.

    -   Toto sestavení obvykle má název, který končí textem ". DSL.dll".

    -   Pokud máte přístup k projektu DSL, můžete nějakého najít soubor sestavení v adresáři **Dsl\bin\\\***

    -   Pokud máte přístup k souboru DSL VSIX, můžete nějakého najít sestavení tak, že změníte příponu názvu souboru VSIX souboru na "zip". Dekomprimujte soubor .zip.

3.  Přidejte odkazy na následující sestavení .NET:

    -   Microsoft.VisualStudio.Modeling.Sdk.11.0.dll

    -   Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0.dll

    -   Microsoft.VisualStudio.Modeling.Sdk.Shell.11.0.dll

    -   System.ComponentModel.Composition.dll

    -   System.Windows.Forms.dll

4.  Vytvoření projektu VSIX ve stejném řešení. Chcete-li to provést, v **nový projekt** dialogové okno, rozbalte seznam **jazyka Visual Basic** nebo **Visual C#**, klikněte na tlačítko **rozšiřitelnost**a potom vyberte  **Projekt VSIX**.

5.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt VSIX a pak klikněte na tlačítko **nastavit jako spouštěný projekt**.

6.  V novém projektu, otevřete **source.extension.vsixmanifest**.

7.  Klikněte na tlačítko **přidávat obsah**. V dialogovém okně Nastavení **typ obsahu** k **Komponenta MEF**, a **zdroj projektu** do projektu knihovny tříd.

8.  Přidáte odkaz na DSL VSIX.

    1.  V **source.extension.vsixmanifest**, klikněte na tlačítko **přidání odkazu**

    2.  V dialogovém okně klikněte na **přidat datová část** a vyhledejte soubor VSIX DSL. Soubor VSIX je součástí řešení DSL v **DslPackage\bin\\\***.

         Díky tomu mají uživatelé nainstalovat DSL a rozšíření ve stejnou dobu. Pokud uživatel již nainstalována DSL, nainstaluje se jenom rozšíření.

9. Zkontrolovat a aktualizovat v ostatních polích **source.extension.vsixmanifest**. Klikněte na tlačítko **vyberte edice** a ověřte, že správný [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] edice jsou nastavené.

10. Přidávání kódu do projektu knihovny tříd. V příkladech v další části použijte jako vodítko.

     Můžete přidat libovolný počet příkaz gesto a ověření třídy.

11. Chcete-li otestovat rozšíření, stiskněte **F5**. V experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], vytvořit nebo otevřít příklad souboru DSL.

## <a name="writing-mef-extensions-for-dsls"></a>Zápis MEF rozšíření pro DSL, linky
 Můžete napsat rozšíření v projektu kódu sestavení samostatné řešení DSL rozšíření. Můžete také použít MEF ve vašem projektu DslPackage jako vhodný způsob k zápisu příkazů, gesta a ověřovacího kódu v rámci DSL.

### <a name="menu-commands"></a>Příkazy nabídky
 Zápis příkazu nabídky, definice třídy, která implementuje <xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement.ICommandExtension> a předpony třída tímto atributem, která je definována v vaší DSL, s názvem *YourDsl*`CommandExtension`. Můžete napsat více než jednu třídu příkaz nabídky.

 `QueryStatus()` je volána, když kliknutí pravým tlačítkem na obrázku. Doporučujeme zkontrolovat aktuální výběr a nastavit `command.Enabled` k označení, když je použít příkaz.

```
using System.ComponentModel.Composition;
using System.Linq;
using Company.MyDsl; // My DSL
using Company.MyDsl.ExtensionEnablement; // My DSL
using Microsoft.VisualStudio.Modeling; // Transactions
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement; // IVsSelectionContext
using Microsoft.VisualStudio.Modeling.ExtensionEnablement; // ICommandExtension

namespace MyMefExtension
{
  // Defined in Dsl\MefExtension\DesignerExtensionMetaDataAttribute.cs:
  [MyDslCommandExtension]
  public class MyCommandClass : ICommandExtension
  {
    /// <summary>
    /// Provides access to current document and selection.
    /// </summary>
    [Import]
    IVsSelectionContext SelectionContext { get; set; }

    /// <summary>
    /// Called when the user selects this command.
    /// </summary>
    /// <param name="command"></param>
    public void Execute(IMenuCommand command)
    {
      // Transaction is required if you want to update elements.
      using (Transaction t = SelectionContext.CurrentStore
              .TransactionManager.BeginTransaction("fix names"))
      {
        foreach (ExampleShape shape in SelectionContext.CurrentSelection)
        {
          ExampleElement element = shape.ModelElement as ExampleElement;
          element.Name = element.Name + " !";
        }
        t.Commit();
      }
    }

    /// <summary>
    /// Called when the user right-clicks the diagram.
    /// Determines whether the command should appear.
    /// This method should set command.Enabled and command.Visible.
    /// </summary>
    /// <param name="command"></param>
    public void QueryStatus(IMenuCommand command)
    {
      command.Enabled =
        command.Visible = (SelectionContext.CurrentSelection.OfType<ExampleShape>().Count() > 0);
    }

    /// <summary>
    /// Called when the user right-clicks the diagram.
    /// Determines the text of the command in the menu.
    /// </summary>
    public string Text
    {
      get { return "My menu command"; }
    }
  }
}

```

### <a name="gesture-handlers"></a>Gesto obslužné rutiny
 Obslužné rutiny gest můžete řešit objekty přetáhli diagram odkudkoli, uvnitř nebo vně [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Následující příklad umožňuje uživateli přetáhněte soubory z Průzkumníka Windows do diagramu. Vytvoří elementy, které obsahují názvy souborů.

 Můžete napsat obslužné rutiny, jak nakládat s drags z jiných DSL modely a modely UML. Další informace najdete v tématu [postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md).

```

using System.ComponentModel.Composition;
using System.Linq;
using Company.MyDsl;
using Company.MyDsl.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling; // Transactions
using Microsoft.VisualStudio.Modeling.Diagrams;
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;

namespace MefExtension
{
  [MyDslGestureExtension]
  class MyGestureExtension : IGestureExtension
  {
    public void OnDoubleClick(ShapeElement targetElement, DiagramPointEventArgs diagramPointEventArgs)
    {
      System.Windows.Forms.MessageBox.Show("double click!");
    }

    /// <summary>
    /// Called when the user drags anything over the diagram.
    /// Return true if the dragged object can be dropped on the current target.
    /// </summary>
    /// <param name="targetMergeElement">The shape or diagram that the mouse is currently over</param>
    /// <param name="diagramDragEventArgs">Data about the dragged element.</param>
    /// <returns></returns>
    public bool CanDragDrop(ShapeElement targetMergeElement, DiagramDragEventArgs diagramDragEventArgs)
    {
      // This handler only allows items to be dropped onto the diagram:
      return targetMergeElement is MefDsl2Diagram &&
      // And only accepts files dragged from Windows Explorer:
        diagramDragEventArgs.Data.GetFormats().Contains("FileNameW");
    }

    /// <summary>
    /// Called when the user drops an item onto the diagram.
    /// </summary>
    /// <param name="targetDropElement"></param>
    /// <param name="diagramDragEventArgs"></param>
    public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)
    {
      MefDsl2Diagram diagram = targetDropElement as MefDsl2Diagram;
      if (diagram == null) return;

      // This handler only accepts files dragged from Windows Explorer:
      string[] draggedFileNames = diagramDragEventArgs.Data.GetData("FileNameW") as string[];
      if (draggedFileNames == null || draggedFileNames.Length == 0) return;

      using (Transaction t = diagram.Store.TransactionManager.BeginTransaction("file names"))
      {
        // Create an element to represent each file:
        foreach (string fileName in draggedFileNames)
        {
          ExampleElement element = new ExampleElement(diagram.ModelElement.Partition);
          element.Name = fileName;

          // This method of adding the new element allows the position
          // of the shape to be specified:
          ElementGroup group = new ElementGroup(element);
          diagram.ElementOperations.MergeElementGroupPrototype(
            diagram, group.CreatePrototype(), PointD.ToPointF(diagramDragEventArgs.MousePosition));
        }
        t.Commit();
      }
    }
  }
}

```

### <a name="validation-constraints"></a>Omezení ověřování
 Metody ověřování jsou označené nástrojem `ValidationExtension` atribut, který se generuje DSL a také pomocí <xref:Microsoft.VisualStudio.Modeling.Validation.ValidationMethodAttribute>. Metoda se může zobrazit v žádné třídě, která není označená atributu.

 Další informace najdete v tématu [ověření v jazyce specifické pro doménu](../modeling/validation-in-a-domain-specific-language.md).

```
using Company.MyDsl;
using Company.MyDsl.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling.Validation;

namespace MefExtension
{
  class MyValidationExtension // Can be any class.
  {
    // SAMPLE VALIDATION METHOD.
    // All validation methods have the following attributes.

    // Specific to the extended DSL:
    [MyDslValidationExtension]

    // Determines when validation is applied:
    [ValidationMethod(
       ValidationCategories.Save
     | ValidationCategories.Open
     | ValidationCategories.Menu)]

    /// <summary>
    /// When validation is executed, this method is invoked
    /// for every element in the model that is an instance
    /// of the second parameter type.
    /// </summary>
    /// <param name="context">For reporting errors</param>
    /// <param name="elementToValidate"></param>
    private void ValidateClassNames
      (ValidationContext context,
       // Type determines to what elements this will be applied:
       ExampleElement elementToValidate)
    {
      // Write code here to test values and links.
      if (elementToValidate.Name.IndexOf(' ') >= 0)
      {
        // Log any unacceptable values:
        context.LogError(
          // Description:
          "Name must not contain spaces"
          // Error code unique to this type of error:
          , "MyDsl001"
          // Element to highlight when user double-clicks error:
          , elementToValidate);
} } } }

```

## <a name="see-also"></a>Viz také

- [Odesílání rozšíření sady Visual Studio](../extensibility/shipping-visual-studio-extensions.md)
- [MEF (Managed Extensibility Framework)](/dotnet/framework/mef/index)
- [Postupy: Přidání obslužné rutiny operace přetažení myší](../modeling/how-to-add-a-drag-and-drop-handler.md)
- [Ověřování v jazyce specifickém pro doménu](../modeling/validation-in-a-domain-specific-language.md)