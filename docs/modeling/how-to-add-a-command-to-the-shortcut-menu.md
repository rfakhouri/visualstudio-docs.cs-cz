---
title: 'Postupy: Přidání příkazu do místní nabídky'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2412e50279c646190d1112a42c00da06c75bf794
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="how-to-add-a-command-to-the-shortcut-menu"></a>Postupy: Přidání příkazu do místní nabídky
Příkazy nabídky můžete přidat do jazyka specifické pro doménu (DSL) tak, aby vaši uživatelé můžete provádět úlohy, které jsou specifické pro vaše DSL. Při kliknutí pravým tlačítkem myši v diagramu se zobrazují příkazy v nabídce kontextu (místní). Příkaz můžete definovat, aby se zobrazí pouze v nabídce v konkrétních situacích. Například můžete provést příkaz viditelná jenom v případě, že uživatel klikne na konkrétní typy elementu nebo elementů v konkrétní stavy.

 Souhrnně kroky jsou prováděny v projektu DslPackage následovně:

1.  [Declare – příkaz do Commands.vsct](#VSCT)

2.  [Aktualizovat číslo verze balíčku v Package.tt](#version). Je nutné provést při každé změně Commands.vsct

3.  [Zápis metod ve třídě CommandSet](#CommandSet) zpřístupněte příkazu a definovat, co má provést příkaz.

 Ukázky najdete [vizualizace a modelování SDK web](http://go.microsoft.com/fwlink/?LinkID=185579).

> [!NOTE]
>  Můžete také upravit chování některé existující příkazy, jako je vyjmutí, vložení, vyberte všechny a tisk přepsáním metody v CommandSet.cs. Další informace najdete v tématu [postupy: Úprava standardních příkazů nabídky](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).

## <a name="defining-a-command-using-mef"></a>Definování příkazu pomocí rozhraní MEF
 Spravovaná rozšíření Framework (MEF) poskytuje alternativní metoda pro definice příkazy nabídky v nabídce diagram. Jeho primárním účelem je umožnit DSL potřeba rozšířit vámi nebo jiných stran. Uživatele můžete nainstalovat jenom DSL, nebo můžete nainstalovat DSL i rozšíření. MEF však také snižuje práci při definování příkazy místní nabídky po počáteční pracovní povolit MEF na DSL.

 V tomto tématu použijte metodu, pokud:

1.  Chcete definovat příkazy nabídky v nabídkách než místní nabídce klikněte pravým tlačítkem.

2.  Chcete definovat konkrétní seskupení příkazů v nabídce.

3.  Nechcete umožnit další osoby mohly rozšířit DSL s vlastní příkazy.

4.  Chcete pouze definovat jeden příkaz.

 Jinak zvažte použití metodu MEF definovat příkazy. Další informace najdete v tématu [rozšíření vaší DSL pomocí MEF](../modeling/extend-your-dsl-by-using-mef.md).

##  <a name="VSCT"></a> Declare – příkaz do Commands.Vsct
 Příkazy nabídky jsou deklarované v DslPackage\Commands.vsct. Tyto definice zadat popisky položek nabídky a jejich umístění v nabídkách.

 Soubor, který chcete upravit, Commands.vsct, naimportuje definice z několika souborů .h, které jsou umístěné v adresáři *Visual Studio SDK instalační cesty*\VisualStudioIntegration\Common\Inc. Zahrnuje také GeneratedVsct.vsct, která se generují z vaší DSL definice.

 Další informace o souborech .vsct najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).

#### <a name="to-add-the-command"></a>Chcete-li přidat příkaz

1.  V **Průzkumníku řešení**v části **DslPackage** projektu, otevřete Commands.vsct.

2.  V `Commands` elementu, definujte jedno nebo více tlačítek a skupinu. A *tlačítko* je položku v nabídce. A *skupiny* je oddíl v nabídce. Pokud chcete definovat tyto položky, přidejte následující prvky:

    ```
    <!-- Define a group - a section in the menu -->
    <Groups>
      <Group guid="guidCustomMenuCmdSet" id="grpidMyMenuGroup" priority="0x0100">
        <!-- These symbols are defined in GeneratedVSCT.vsct -->
        <Parent guid="guidCmdSet" id="menuidContext" />
      </Group>
    </Groups>
    <!-- Define a button - a menu item - inside the Group -->
    <Buttons>
      <Button guid="guidCustomMenuCmdSet" id="cmdidMyContextMenuCommand"
        priority="0x0100" type="Button">
        <Parent guid="guidCustomMenuCmdSet" id="grpidMyMenuGroup"/>
        <!-- If you do not want to place the command in your own Group,
             use Parent guid="guidCmdSet" id="grpidContextMain".
             These symbols are defined in GeneratedVSCT.vsct -->
        <CommandFlag>DynamicVisibility</CommandFlag>
        <Strings>
          <ButtonText>My Context Menu Command</ButtonText>
        </Strings>
      </Button>
    </Buttons>
    ```

    > [!NOTE]
    >  Každé tlačítko nebo skupině je identifikovaná identifikátorem GUID a identifikátor celé číslo. Můžete vytvořit několik skupin a tlačítka se stejným identifikátorem GUID. Musí však mít různé identifikátory. Identifikátor GUID názvy a ID názvy jsou převedeny na skutečné identifikátory GUID a číselné ID `<Symbols>` uzlu.

3.  Přidáte omezení viditelnosti pro příkaz tak, aby je načten jen v kontextu jazyka specifické pro doménu. Další informace najdete v tématu [VisibilityConstraints Element](../extensibility/visibilityconstraints-element.md).

     Chcete-li to provést, přidejte následující prvky v `CommandTable` element po `Commands` element.

    ```
    <VisibilityConstraints>
      <!-- Ensures the command is only loaded for this DSL -->
      <VisibilityItem guid="guidCustomMenuCmdSet" id="cmdidMyContextMenuCommand"
        context="guidEditor"/>
    </VisibilityConstraints>
    ```

4.  Zadejte názvy, které jste použili pro identifikátory a identifikátory GUID. Chcete-li to provést, přidejte `Symbols` element v `CommandTable` element po `Commands` elementu.

    ```
    <Symbols>
      <!-- Substitute a unique GUID for the placeholder: -->
      <GuidSymbol name="guidCustomMenuCmdSet"
        value="{00000000-0000-0000-0000-000000000000}" >
        <IDSymbol name="grpidMyMenuGroup" value="0x01001"/>
        <IDSymbol name="cmdidMyContextMenuCommand" value="0x00001"/>
      </GuidSymbol>
    </Symbols>
    ```

5.  Nahraďte `{000...000}` s identifikátorem GUID, který identifikuje skupin a položek nabídky. Můžete získat nový identifikátor GUID **vytvořit GUID** ve **nástroje** nabídky.

    > [!NOTE]
    >  Pokud přidáte další skupiny nebo položky nabídky, můžete použít stejný identifikátor GUID. Však musíte použít nové hodnoty pro `IDSymbols`.

6.  V kódu, který jste zkopírovali z tohoto postupu nahraďte všechny výskyty následující řetězce vlastní řetězce:

    -   `grpidMyMenuGroup`

    -   `cmdidMyContextMenuCommand`

    -   `guidCustomMenuCmdSet`

    -   `My Context Menu Command`

##  <a name="version"></a> Aktualizovat číslo verze balíčku v Package.tt
 Kdykoli můžete přidat nebo změnit příkaz, aktualizovat `version` parametr <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> který se použije k třídě balíčku před vydání nové verze jazyka specifické pro doménu.

 Protože třída balíčku je definováno v to generovaný soubor, aktualizujte atribut v textovém souboru šablony, který generuje soubor Package.cs.

#### <a name="to-update-the-packagett-file"></a>Aktualizace souboru Package.tt

1.  V **Průzkumníku řešení**v **DslPackage** v projektu **GeneratedCode** složku, otevřete soubor Package.tt.

2.  Vyhledejte `ProvideMenuResource` atribut.

3.  Přírůstek `version` parametr pro atribut, který je druhý parametr. Pokud chcete, můžete napsat název parametru explicitně chcete upozorňovat na jeho účel. Příklad:

     `[VSShell::ProvideMenuResource("1000.ctmenu", version: 2 )]`

##  <a name="CommandSet"></a> Zadejte chování příkazu
 Vaše DSL již některé příkazy, které jsou implementované v částečné třídu, která je deklarován v DslPackage\GeneratedCode\CommandSet.cs. Pokud chcete přidat nové příkazy, musíte rozšířit tato třída tak, že vytvoříte nový soubor, který obsahuje deklaraci částečné stejné třídy. Název třídy je obvykle  *\<YourDslName >*`CommandSet`. Je vhodné, začněte tím, že ověření název třídy a zkontrolujete jeho obsah.

 Příkaz set – třída je odvozený od <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet>.

#### <a name="to-extend-the-commandset-class"></a>Rozšíření třídy CommandSet

1.  V Průzkumníku řešení v projektu DslPackage otevřete složku GeneratedCode a podívejte se do části CommandSet.tt a otevřete jeho generovaný soubor CommandSet.cs. Všimněte si, obor názvů a název první třídy, která je definována existuje. Například může zobrazit:

     `namespace Company.Language1`

     `{ ...  internal partial class Language1CommandSet : ...`

2.  V **DslPackage**, vytvořte složku s názvem **vlastní kód**. V této složce vytvořte nový soubor třídy s názvem `CommandSet.cs`.

3.  V novém souboru zápisu částečné deklarace, který má stejný obor názvů a název jako generovaný třídu. Příklad:

     `namespace Company.Language1 /* Make sure this is correct */`

     `{ internal partial class Language1CommandSet { ...`

     **Poznámka:** Pokud šablona třídy jste použili k vytvoření nového souboru, je nutné opravit obor názvů a název třídy.

### <a name="extend-the-command-set-class"></a>Rozšíření třídy sady příkazů
 Příkaz set kódu bude obvykle nutné importovat následující obory názvů:

```
using System;
using System.Collections.Generic;
using System.ComponentModel.Design;
using System.Linq;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;
using Microsoft.VisualStudio.Modeling.Shell;
```

 Nastavte obor názvů a název třídy tak, aby odpovídaly programů v generované CommandSet.cs:

```
namespace Company.Language1 /* Make sure this is correct */
{
  // Same class as the generated class.
  internal partial class Language1CommandSet
  {
```

 Musíte definovat dvě metody, jeden k určení, kdy příkaz bude zobrazovat na místní nabídky a druhým k provedení příkazu. Tyto metody nejsou přepsání; Místo toho je zaregistrujete v seznam příkazů.

### <a name="define-when-the-command-will-be-visible"></a>Zadejte, kdy budou viditelné příkaz
 U každého příkazu, zadejte `OnStatus...` metoda, která určuje, zda příkaz zobrazí se v nabídce, a zda bude povoleno nebo šedá. Nastavte `Visible` a `Enabled` vlastnosti `MenuCommand`, jak je znázorněno v následujícím příkladu. Tato metoda je volána, aby bylo možné vytvořit místní nabídky pokaždé, když kliknutí pravým tlačítkem na obrázku, musí rychle pracovat.

 V tomto příkladu je příkaz viditelná jenom v případě, že uživatel vybral konkrétní typ tvar a je povolená jenom v případě alespoň jeden z vybraných elementů je v určitém stavu. V příkladu je založený na šabloně DSL diagramu tříd a ClassShape a ModelClass jsou typy, které jsou definovány v DSL:

```
private void OnStatusMyContextMenuCommand(object sender, EventArgs e)
{
  MenuCommand command = sender as MenuCommand;
  command.Visible = command.Enabled = false;
  foreach (object selectedObject in this.CurrentSelection)
  {
    ClassShape shape = selectedObject as ClassShape;
    if (shape != null)
    {
      // Visibility depends on what is selected.
      command.Visible = true;
      ModelClass element = shape.ModelElement as ModelClass;
      // Enabled depends on state of selection.
      if (element != null && element.Comments.Count == 0)
      {
        command.Enabled = true;
        return; // seen enough
} } } }
```

 Následující fragmenty jsou často užitečné v OnStatus metody:

-   `this.CurrentSelection`. Obrazec, který uživatel klepli pravým tlačítkem myši je vždy zahrnuté v tomto seznamu. Pokud uživatel klikne na prázdnou část diagramu, diagramu je pouze členem seznamu.

-   `this.IsDiagramSelected()` - `true` Pokud uživatel klikne na prázdnou část diagramu.

-   `this.IsCurrentDiagramEmpty()`

-   `this.IsSingleSelection()` -uživatel nevybrali více objektů

-   `this.SingleSelection` -tvar nebo diagram, který klepli pravým tlačítkem myši uživatele

-   `shape.ModelElement as MyLanguageElement` -element modelu reprezentována obrazce.

 V rámci obecných pokynů, zkontrolujte `Visible` vlastnost závisí na výběr a ujistěte se, `Enabled` vlastnost závisí na stav vybrané elementy.

 Metodu OnStatus nesmí změnit stav úložiště.

### <a name="define-what-the-command-does"></a>Definovat, jaké příkaz
 U každého příkazu, zadejte `OnMenu...` metoda, která provádí požadované akce, když uživatel klikne příkaz nabídky.

 Pokud provedete změny elementů modelu, musíte tak učinit v transakci. Další informace najdete v tématu [postupy: Úprava standardních příkazů nabídky](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).

 V tomto příkladu `ClassShape`, `ModelClass`, a `Comment` jsou typy, které jsou definovány v DSL, která jsou odvozená z třídy Diagram DSL šablony.

```
private void OnMenuMyContextMenuCommand(object sender, EventArgs e)
{
  MenuCommand command = sender as MenuCommand;
  Store store = this.CurrentDocData.Store;
  // Changes to elements and shapes must be performed in a Transaction.
  using (Transaction transaction =
       store.TransactionManager.BeginTransaction("My command"))
  {
    foreach (object selectedObject in this.CurrentSelection)
    {
      // ClassShape is defined in my DSL.
      ClassShape shape = selectedObject as ClassShape;
      if (shape != null)
      {
        // ModelClass is defined in my DSL.
        ModelClass element = shape.ModelElement as ModelClass;
        if (element != null)
        {
          // Do required action here - for example:

          // Create a new element. Comment is defined in my DSL.
          Comment newComment = new Comment(element.Partition);
          // Every element must be the target of an embedding link.
          element.ModelRoot.Comments.Add(newComment);
          // Set properties of new element.
          newComment.Text = "This is a comment";
          // Create a reference link to existing object.
          element.Comments.Add(newComment);
        }
      }
    }
    transaction.Commit(); // Don't forget this!
  }
}
```

 Další informace o tom, jak přejít z objektu na objekt v modelu a o tom, jak vytvořit objekty a propojení najdete v tématu [postupy: Úprava standardních příkazů nabídky](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).

### <a name="register-the-command"></a>Zaregistrovat příkaz
 Opakujte v jazyce C# deklarace GUID a s ID hodnoty, které jste udělali v části symboly CommandSet.vsct:

```
private Guid guidCustomMenuCmdSet =
    new Guid("00000000-0000-0000-0000-000000000000");
private const int grpidMyMenuGroup = 0x01001;
private const int cmdidMyContextMenuCommand = 1;
```

 Použít stejnou hodnotu GUID, jako jste vložili v **Commands.vsct**.

> [!NOTE]
>  Pokud změníte části symboly souboru VSCT, musíte změnit taky tyto deklarace tak, aby odpovídaly. By se měl také zvýšit číslo verze v Package.tt

 Zaregistrujte vaše příkazy nabídky jako součást sady tento příkaz. `GetMenuCommands()` je volána po při inicializaci diagramu:

```
protected override IList<MenuCommand> GetMenuCommands()
{
  // Get the list of generated commands.
  IList<MenuCommand> commands = base.GetMenuCommands();
  // Add a custom command:
  DynamicStatusMenuCommand myContextMenuCommand =
    new DynamicStatusMenuCommand(
      new EventHandler(OnStatusMyContextMenuCommand),
      new EventHandler(OnMenuMyContextMenuCommand),
      new CommandID(guidCustomMenuCmdSet, cmdidMyContextMenuCommand));
  commands.Add(myContextMenuCommand);
  // Add more commands here.
  return commands;
}
```

## <a name="test-the-command"></a>Testování příkaz
 Sestavte a spusťte DSL v instanci experimentální sady Visual Studio. Příkaz objevit v místní nabídce v situacích, které jste zadali.

#### <a name="to-exercise-the-command"></a>Vykonávat příkaz

1.  Na **Průzkumníku řešení** nástrojů klikněte na tlačítko **transformaci všech šablon**.

2.  Stiskněte klávesu **F5** znovu sestavte řešení, a spusťte ladění jazyka domény experimentální sestavení.

3.  V experimentální sestavení otevřete Ukázka diagramu.

4.  Klikněte pravým tlačítkem na různé položky v diagramu na ověřte, zda příkaz je správně povolené nebo zakázané a odpovídajícím způsobem zobrazí nebo skryté, v závislosti na vybrané položky.

## <a name="troubleshooting"></a>Poradce při potížích
 **Příkaz se nezobrazí v nabídce:**

-   Příkaz se objeví jenom v ladění instancí sady Visual Studio, dokud nenainstalujete DSL balíčku. Další informace najdete v tématu [nasazení řešení jazyk specifické pro doménu](../modeling/deploying-domain-specific-language-solutions.md).

-   Ujistěte se, že experimentální ukázky má příponu názvu souboru správné pro tento DSL. Chcete-li zkontrolovat příponu názvu souboru, otevřete DslDefinition.dsl v hlavní instanci sady Visual Studio. V Průzkumníku DSL, klikněte pravým tlačítkem na uzel Editor a pak klikněte na položku Vlastnosti. V okně Vlastnosti zkontrolujte vlastnost FileExtension.

-   Jste [zvýšíte číslo verze balíčku](#version)?

-   Na začátku metodu OnStatus nastavte zarážky. Měli přerušení, když kliknete pravým tlačítkem na libovolnou část diagramu.

     **OnStatus metoda není volána**:

    -   Ujistěte se, že identifikátory v kódu CommandSet a identifikátory GUID shodovat s hodnotami v části symboly Commands.vsct.

    -   Commands.vsct Ujistěte se, že identifikátor GUID a ID v každé nadřazený uzel identifikovat správné nadřazené skupiny.

    -   Do příkazového řádku Visual Studia zadejte devenv/Setup exp /rootsuffix. Potom restartujte ladění instanci sady Visual Studio.

-   Projděte OnStatus metodu k ověření tohoto příkazu. A příkaz viditelný. Povolené jsou nastavené na hodnotu true.

 **Nesprávný nabídky text se zobrazí, nebo příkazu se zobrazí v nesprávném místě**:

-   Ujistěte se, že kombinace GUID a ID je jedinečný pro tento příkaz.

-   Ujistěte se, že jste odinstalovali starší verze balíčku.

## <a name="see-also"></a>Viz také

- [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)
- [Postupy: úprava příkazu standardní nabídky](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md)
- [Nasazení řešení jazyka specifického pro doménu](../modeling/deploying-domain-specific-language-solutions.md)
- [Ukázkový kód: okruh diagramy](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]