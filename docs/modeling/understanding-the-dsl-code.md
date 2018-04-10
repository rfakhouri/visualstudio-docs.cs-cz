---
title: Pochopení kódu DSL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, generated code
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 41cf1f19e03c1197c6266b5057af993b677c9c53
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="understanding-the-dsl-code"></a>Porozumění kódu DSL
Jazyk specifické pro doménu DSL řešení generuje rozhraní API, které můžete použít ke čtení a aktualizovat instance DSL v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Toto rozhraní API je definována v kód, který se vygeneruje z definice DSL. Toto téma popisuje generovaného rozhraní API.  
  
## <a name="the-example-solution-component-diagrams"></a>Příklad řešení: diagramy komponent  
 Vytvářet řešení, která je zdrojem většinu v příkladech v tomto tématu, vytvořit DSL z **součást modely** šablona řešení. Toto je jedna z standardní šablony, které se zobrazí, když vytvoříte nové řešení DSL.  
  
> [!NOTE]
>  Diagramy komponent UML, které můžete vytvořit v sadě Visual Studio pomocí nabídky architektura nesouvisí součást diagramy DSL šablony. V **nový projekt** dialogové okno, rozbalte seznam **jiný projekt Types\Extensibility** a pak klikněte na **Návrhář jazyk specifické pro doménu**.  
  
 Stisknutím klávesy F5 a experiment, pokud nejste obeznámeni s touto šablonou řešení. Všimněte si zejména vytvořit portů přetažením nástroj port na komponentu a že se můžete připojit porty.  
  
 ![Součásti a vzájemně propojena porty](../modeling/media/componentsample.png "ComponentSample")  
  
## <a name="the-structure-of-the-dsl-solution"></a>Struktura řešení DSL  
 **Dsl** projektu definuje rozhraní API pro vaše DSL. **DslPackage** projektu definuje, jak se integruje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Můžete také přidat vlastní projekty, které může také obsahovat kód, který vygenerovala z modelu.  
  
### <a name="the-code-directories"></a>Kód adresáře  
 Většinu kódu v každé z těchto projektů se generují z **Dsl\DslDefinition.dsl**. Generovaný kód je v **vygeneruje kód** složky. Chcete-li zobrazit to generovaný soubor, klikněte na tlačítko **[+]** vedle generování **.tt** souboru.  
  
 Doporučujeme vám, že si prohlédnout generovaného kódu, které vám pomohou pochopit DSL. Pokud chcete zobrazit soubory, rozbalte soubory *.tt v Průzkumníku řešení.  
  
 \*Soubory .tt obsahují velmi malé generování kódu. Místo toho použijte `<#include>` direktivy zahrnout soubory sdíleného šablony. Sdílené soubory naleznete v **\Program Files\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft\DSL SDK\DSL Designer\11.0\TextTemplates**  
  
 Když přidáte vlastní kód programu k řešení DSL, přidejte ji do samostatného souboru mimo složku vygenerovat kód. Můžete chtít vytvořit **vlastní kód** složky. (Při přidání nového souboru kódu na vlastní složku, nezapomeňte opravte oboru názvů v kostře počáteční kód.)  
  
 Důrazně doporučujeme generovaný kód přímo, neupravujte vzhledem k tomu, že vaše úpravy budou ztraceny, když znovu sestavte řešení. Místo toho k přizpůsobení vaší DSL:  
  
-   Upravte mnoho parametrů v definici DSL.  
  
-   Částečné třídy v souborech samostatné kódu k zápisu do přepsání metody, které jsou definované v nebo zdědí, vygenerované třídy. V některých případech je nutné nastavit **generuje dvojité odvozené** možnost třídy v definici DSL, aby bylo možné přepsat generovaného metoda.  
  
-   Nastavení možností v definici DSL, který způsobit, že generovaný kód pro 'háky' přinášejí vlastní kód.  
  
     Například pokud nastavíte **má vlastní konstruktor** možnost třídy domény a následně vytvořit řešení, zobrazí se chybové zprávy. Když dvakrát kliknete na jednu z těchto chybové zprávy, zobrazí se komentáře v generovaného kódu, které vysvětlují, co by měly poskytnout vlastní kód.  
  
-   Zápis textu šablony pro generování kódu, které jsou specifické pro vaši aplikaci. Vám může použít obsahovat soubory a sdílet části šablony, které jsou společné pro mnoha projektů a můžete vytvořit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] šablony nastavit projekty, které jsou inicializovány s strukturu souboru projektu.  
  
## <a name="generated-files-in-dsl"></a>Generované soubory v Dsl  
 Následující soubory generované se zobrazí v **Dsl** projektu.  
  
 *YourDsl* `Schema.xsd`  
  
 Schéma pro soubory, který obsahuje instance vaší DSL. Tento soubor se zkopíruje do kompilace (**bin**) adresáře. Když instalujete vaší DSL, můžete zkopírovat tento soubor do **\Program Files\Microsoft Visual Studio 11.0\Xml\Schemas** tak, aby soubory modelu může být ověřen. Další informace najdete v tématu [nasazení řešení jazyk specifické pro doménu](../modeling/deploying-domain-specific-language-solutions.md).  
  
 Pokud upravíte serializace nastavením možnosti v Průzkumníku DSL, schéma se změní. Však můžete psát vlastní kód serializace, tento soubor může už představují skutečné schématu. Další informace najdete v tématu [přizpůsobení File Storage a serializace XML](../modeling/customizing-file-storage-and-xml-serialization.md).  
  
 `ConnectionBuilders.cs`  
  
 Tvůrce připojení je třída, která vytvoří vztahy. Je kód za nástroj pro připojení. Tento soubor obsahuje pár třídy pro každý nástroj pro připojení. Jejich názvy jsou odvozeny od názvů domény relace a připojení nástroj: *vztah*tvůrce, a *ConnectorTool*ConnectAction.  
  
 (V příkladu součást řešení pro jeden z připojení počítačů se nazývá ConnectionBuilder, to je shoda, protože relace domény má název připojení.)  
  
 Relace je vytvořen v *vztah* `Builder.Connect()` metoda. Výchozí verze ověří, že jsou přijatelné elementů modelu zdroje a cíle a potom vytvoří relaci. Příklad:  
  
 `CommentReferencesSubject(sourceAccepted, targetAccepted);`  
  
 Každá třída tvůrce se generují z uzlu **připojení počítačů** část v Průzkumníku DSL. Jeden `Connect` metoda můžete vytvářet vztahy mezi páry jeden nebo více tříd domény. Každý pár je definována direktivě připojit propojení, které můžete najít v Průzkumníku DSL pod uzlem Tvůrce.  
  
 Můžete například přidat do jednoho připojení Tvůrce direktivy připojit odkaz pro všechny tři typy relace v ukázce DSL. To by poskytnout uživateli nástroj jednoho připojení. Typ vztahu instanci bude záviset na typy zdrojové a cílové elementy vybrané uživatelem.  Přidání direktivy připojit propojení, klikněte pravým tlačítkem na tvůrce v Průzkumníku DSL.  
  
 Chcete-li psát vlastní kód, který je spuštěn při vytvoření určitý typ relace domény, vyberte odpovídající odkaz připojit direktiva pod uzlem Tvůrce. V okně Vlastnosti nastavte **používá vlastní připojení**. Znovu sestavte řešení a potom zadejte kód pro výsledný chyby opravit.  
  
 Chcete-li napsat vlastní kód, který se spustí pokaždé, když uživatel použije tento nástroj pro připojení, nastavte **je vlastní** vlastnost Tvůrce připojení. Můžete zadat kód, který rozhodne, zda je povoleno source element, jestli konkrétní kombinaci zdroje a smí obsahovat cíl a co aktualizace je třeba do modelu při připojení. Například je může povolit připojení pouze v případě, že by vytvořilo smyčku v diagramu. Místo odkaz jeden vztah může vytvořit instanci složitější vzor několik mezi související prvky mezi zdrojem a cílem.  
  
 `Connectors.cs`  
  
 Obsahuje třídy pro konektory, které jsou elementy diagramu, které obvykle představují referenčních relací. Každá třída se generují z jeden konektor v definici DSL. Každá třída konektoru je odvozený od <xref:Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape>  
  
 Chcete-li barvu a některé další funkce proměnnou styl za běhu, klikněte pravým tlačítkem na třídu v diagramu DSL definice a přejděte na **přidat zveřejněné**.  
  
 Chcete-li další styl funkce proměnné v době běhu, najdete v části například <xref:Microsoft.VisualStudio.Modeling.Diagrams.TextField> a <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement>.  
  
 `Diagram.cs`  
  
 Obsahuje třídy, která definuje diagramu. Je odvozený od <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>.  
  
 Chcete-li barvu a některé další funkce proměnnou styl za běhu, klikněte pravým tlačítkem na třídu v diagramu DSL definice a přejděte na **přidat zveřejněné**.  
  
 Kromě toho tento soubor obsahuje `FixupDiagram` pravidlo, které odpovídá při přidání nového elementu do modelu. Pravidlo přidá nový tvar a tvar, který odkazuje na element modelu.  
  
 `DirectiveProcessor.cs`  
  
 Tato procesoru direktiv pomáhá uživatelům zapisovat textové šablony, které čtou instanci vaše DSL. Načte sestavení (DLL) pro vaše DSL procesoru direktiv a efektivně vloží `using` příkazy pro obor názvů. To umožňuje kód v textové šablony k používání tříd a vztahů, které jste definovali ve vašem DSL.  
  
 Další informace najdete v tématu [generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md) a [vytváření vlastní T4 Text šablony direktiva procesorů](../modeling/creating-custom-t4-text-template-directive-processors.md).  
  
 `DomainClasses.cs`  
  
 Implementace třídy domény, které jste definovali, včetně abstraktní třídy a kořenová třída modelu. Jsou odvozeny od <xref:Microsoft.VisualStudio.Modeling.ModelElement>.  
  
 Každá třída domény obsahuje:  
  
-   Definici vlastnosti a třídu vnořené obslužné rutiny pro každou vlastnost domény. Můžete přepsat OnValueChanging() a OnValueChanged(). Další informace najdete v tématu [domény obslužné rutiny změnit hodnotu vlastnosti](../modeling/domain-property-value-change-handlers.md).  
  
     V příkladu DSL `Comment` třída obsahuje vlastnost `Text` a třídu obslužné rutiny `TextPropertyHandler`.  
  
-   Přistupující objekt vlastnosti u relací, ve kterých se účastní Tato třída domény. (Neexistuje žádná třída vnořených vlastností role.)  
  
     V příkladu DSL `Comment` třída má přistupující objekty, které přístup k jeho nadřazeného modelu prostřednictvím vnoření relace `ComponentModelHasComments`.  
  
-   Konstruktory. Pokud chcete tyto přepsat, nastavte **má vlastní konstruktor** k třídě domény.  
  
-   Element skupiny prototypu (EGP) obslužná rutina metody. Toto jsou nezbytné, pokud uživatel může *sloučení* (Přidat) jiný element do instance této třídy. Uživatel má typicky to přetažením z nástroj na element nebo jiné tvaru nebo vložením.  
  
     V příkladu může být DSL, Port vstupní nebo výstupní Port sloučeny do komponenty. Navíc můžete součásti a komentáře sloučeny do modelu. Rozhraní  
  
     EGP obslužná rutina metody ve třídě součást povolit součást tak, aby přijímal porty, ale ne komentáře. Obslužná rutina EGP v kořenová třída modelu přijme komentáře a součástí, ale není porty.  
  
 `DomainModel.cs`  
  
 Třída, která představuje modelu domény. Je odvozený od <xref:Microsoft.VisualStudio.Modeling.DomainModel>.  
  
> [!NOTE]
>  To však není stejný jako kořenová třída modelu.  
  
 Kopírování a odstranit uzavření definovat, jaké další prvky by měly být zahrnuty při elementu je zkopírovat nebo odstranit. Toto chování můžete ovládat nastavením **rozšíří kopie** a **rozšíří odstranit** Vlastnosti rolí na každé straně každé relaci. Pokud chcete hodnoty, které mají být dynamicky určit, můžete napsat kód pro přepsání metody třídy uzavření. 
  
 `DomainModelResx.resx`  
  
 Tato položka obsahuje řetězce například popisy domény třídy a vlastnosti, názvy vlastností, popisky sada nástrojů, standardní cíl chybové zprávy a jiných řetězců, které mohou být zobrazeny pro uživatele. Obsahuje taky nástroj ikony a bitové kopie pro bitovou kopii tvarů.  
  
 Tento soubor je vázané na integrovaný sestavení a poskytuje výchozí hodnoty těchto prostředků. Je možné lokalizovat vaší DSL vytvořením satelitní sestavení, která obsahuje lokalizované verzi prostředků. Tuto verzi se použije při instalaci DSL v jazykové verzi odpovídající lokalizované prostředky. Další informace najdete v tématu [nasazení řešení jazyk specifické pro doménu](../modeling/deploying-domain-specific-language-solutions.md).  
  
 `DomainRelationships.cs`  
  
 Každé propojení mezi dvěma prvky v modelu je reprezentovaný instancí třídy vztah domény. Všechny třídy relace jsou odvozeny od <xref:Microsoft.VisualStudio.Modeling.ElementLink>, který je zase odvozen z <xref:Microsoft.VisualStudio.Modeling.ModelElement>. Protože se jedná ModelElement, instance vztahu může mít vlastnosti a může být zdroje nebo cíle vztahu.  
  
 `HelpKeywordHelper.cs`  
  
 Poskytuje funkce, které se použijí při stisknutí klávesy F1.  
  
 `MultiplicityValidation.cs`  
  
 V rolích vztah, kde můžete určit násobnost 1..1 nebo 1.. *, uživatel by měl být upozorněn této aspoň jednu instanci relace je požadovaná. Tento soubor poskytuje omezení ověřování, které implementují upozornění. 1..1 odkaz na nadřazený vnoření není ověřen.  
  
 Pro spuštění těchto omezení, je potřeba mít nastavit jednu z **používá...**  možnosti v **Editor\Validation** uzlu v Průzkumníku DSL. Další informace najdete v tématu [ověření v jazyce specifické pro doménu](../modeling/validation-in-a-domain-specific-language.md).  
  
 `PropertiesGrid.cs`  
  
 Tento soubor obsahuje kód, pouze v případě, že připojené vlastní popisovač typu pro vlastnost domain. Další informace najdete v tématu [přizpůsobení okna vlastnosti](../modeling/customizing-the-properties-window.md).  
  
 `SerializationHelper.cs`  
  
-   Metoda ověření zajistit, že žádné dva elementy odkazují na stejný přezdívka. Další informace najdete v tématu [přizpůsobení File Storage a serializace XML](../modeling/customizing-file-storage-and-xml-serialization.md).  
  
-   SerializationHelper třída, která poskytuje funkce, které používají společné třídy serializace.  
  
 `Serializer.cs`  
  
 Serializátor třída pro každou třídy domény, relace, tvaru, konektor, diagram a modelu.  
  
 Mnoho funkcí těchto tříd se dá nastavit podle nastavení v Průzkumníku DSL pod **chování serializace Xml**.  
  
 `Shapes.cs`  
  
 Třída pro každá třída obrazce v definici DSL. Tvary jsou odvozeny od <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape>. Další informace najdete v tématu [přizpůsobení File Storage a serializace XML](../modeling/customizing-file-storage-and-xml-serialization.md).  
  
 Chcete-li přepsat generovaného metody s vlastními metody v konkrétní třídu, nastavte **generuje dvojité odvozené** pro konektor v definici DSL. Chcete-li nahradit konstruktor vlastní kód, nastavte **má vlastní konstruktor**.  
  
 Chcete-li barvu a některé další funkce proměnnou styl za běhu, klikněte pravým tlačítkem na třídu v diagramu DSL definice a přejděte na **přidat zveřejněné**.  
  
 Chcete-li další styl funkce proměnné v době běhu, najdete v části například <xref:Microsoft.VisualStudio.Modeling.Diagrams.TextField> a <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement>  
  
 `ToolboxHelper.cs`  
  
 Nastaví sady nástrojů nainstalováním element skupiny prototypy do nástroje pro element. Kopie těchto prototypy jsou sloučeny s cílové elementy, když uživatel spustí nástroj.  
  
 Může přepsat `CreateElementPrototype()` k definování položky sady nástrojů, které vytvoří skupinu několik objektů. Můžete třeba definovat položku k reprezentaci objektů, které mají dílčí součásti. Po změně kódu, resetovat experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a vymažte mezipaměť sady nástrojů.  
  
## <a name="generated-files-in-the-dslpackage-project"></a>Generované soubory v projektu DslPackage  
 DslPackage páry v odstupu DSL modelu, který má [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí, spravovat příkazů oken, nabídek a sady nástrojů. Většina tříd jsou dvojité odvozené, tak, aby jejich metod se dá přepsat.  
  
 `CommandSet.cs`  
  
 Příkazy nabídky kontextu, které jsou viditelné v diagramu. Můžete přizpůsobit nebo přidat do této skupiny. Tento soubor obsahuje kód pro příkazy. Umístění příkazů v nabídkách je určen podle Commands.vsct souboru. Další informace najdete v tématu [příkazy zápis uživatele a akce](../modeling/writing-user-commands-and-actions.md).  
  
 `Constants.cs`  
  
 Identifikátory GUID.  
  
 `DocData.cs`  
  
 *YourDsl* `DocData` spravuje načítání a ukládání modelu do souboru a vytvoří instance úložiště.  
  
 Například pokud chcete uložit vaše DSL v databázi místo souboru, může přepíšete `Load` a `Save` metody.  
  
 `DocView.cs`  
  
 *YourDsl* `DocView` spravuje okna, ve kterém se zobrazí diagram. Například může Vložit diagram uvnitř formuláře systému windows:  
  
 Do projektu DslPackage přidáte uživatelský ovládací prvek souboru. Přidejte panelu, ve kterém lze zobrazit diagramu. Přidání tlačítek a jiných ovládacích prvků. V zobrazení kódu formuláře přidejte následující kód, úpravě jména vaší DSL:  
  
```  
using System;  
using System.Collections.Generic;  
using System.ComponentModel;  
using System.Drawing;  
using System.Data;  
using System.Linq;  
using System.Text;  
using System.Windows.Forms;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Shell;  
  
namespace Company.EmbedInForm  
{  
  public partial class UserControl1 : UserControl  
  {  
    public UserControl1()  
    {  
      InitializeComponent();  
    }  
  
    private DiagramDocView docView;  
  
    public UserControl1(DiagramDocView docView, Control content)  
      : this()  
    {  
      this.docView = docView;  
      panel1.Controls.Add(content);  
    }  
  
    private void button1_Click(object sender, EventArgs e)  
    {  
      ExampleModel modelRoot = this.docView.CurrentDiagram.ModelElement as ExampleModel;  
      foreach (ExampleElement element in modelRoot.Elements)  
      {  
       listBox1.Items.Add(element.Name);  
      }  
    }  
  }  
  internal partial class EmbedInFormDocView  
  {  
  
    private ContainerControl container;  
  
    /// <summary>  
    /// Return a User Control instead of the DSL window.   
    /// The user control will contain the DSL window.  
    /// </summary>  
  
    public override System.Windows.Forms.IWin32Window Window  
    {  
      get  
      {  
        if (container == null)  
        {  
          // Put the normal DSL Window inside our control  
          container = new UserControl1(this, (Control)base.Window);  
        }  
        return container;  
      }  
    }  
  }  
  
}  
  
```  
  
 `EditorFactory.cs`  
  
 Vytvoří instanci `DocData` a `DocView`. Vyřizuje standardní rozhraní [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] používá k otevření editoru při spuštění vašeho DSL balíčku. V odkazuje `ProvideEditorFactory` atribut v Package.cs  
  
 `GeneratedVSCT.vsct`  
  
 Vyhledá standardní příkazy v nabídkách, jako je například v místní nabídce diagramu **upravit** nabídky a tak dále. Kód pro příkazy je v CommandSet.cs. Můžete přemístit nebo upravit standardní příkazy a můžete přidat vlastní příkazy. Další informace najdete v tématu [příkazy zápis uživatele a akce](../modeling/writing-user-commands-and-actions.md).  
  
 `ModelExplorer.cs`  
  
 Definuje Průzkumníka modelu pro vaše DSL. Toto je zobrazení stromu modelu, který uživateli se zobrazí vedle diagramu.  
  
 Například může přepsat `InsertTreeView()` Chcete-li změnit pořadí, ve kterém elementy zobrazí v Průzkumníku modelu.  
  
 Pokud chcete výběr v Průzkumníku modelu udržovat synchronizované s výběrem diagramu, můžete použít následující kód:  
  
```  
protected override void OnSelectionChanged(global::System.EventArgs e)  
{  
base.OnSelectionChanged(e);  
// get the selected element  
DslModeling::ModelElement selectedElement =   
this.PrimarySelection as DslModeling::ModelElement;  
// Select in the model explorer  
SelectInModelExplorer<YOURLANGUAGEExplorerToolWindow>(selectedElement);  
}  
private void SelectInModelExplorer<T>(DslModeling::ModelElement modelElement)  
where T : DslShell.ModelExplorerToolWindow  
{  
DslShell::ModelingPackage package =   
this.GetService(typeof(VSShell.Package)) as DslShell::ModelingPackage;  
  
if (package != null)  
{  
// find the model explorer window  
T explorerWindow = package.GetToolWindow(typeof(T), true) as T;  
if (explorerWindow != null)  
{  
// get the tree container  
DslShell.ModelExplorerTreeContainer treeContainer =   
explorerWindow.TreeContainer;  
// find the tree node  
DslShell.ExplorerTreeNode treeNode =   
treeContainer.FindNodeForElement(modelElement);  
// select the node  
explorerWindow.TreeContainer.ObjectModelBrowser.SelectedNode = treeNode;  
}  
}  
}  
  
```  
  
 `ModelExplorerToolWindow.cs`  
  
 Definuje okna, ve kterém se zobrazí Průzkumníku modelu. Výběr položek v Průzkumníku zpracovává.  
  
 `Package.cs`  
  
 Tento soubor definuje, jak DSL integruje do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Atributy pro třídu balíček zaregistrovat DSL jako obslužná rutina pro soubory, které vaše přípona souboru, zadejte její sady nástrojů a definovat, jak otevřete nové okno. Inicializaci() metoda je volána jednou, pokud je první DSL načten do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] instance.  
  
 `Source.extension.vsixmanifest`  
  
 Chcete-li přizpůsobit tohoto souboru, upravte `.tt` souboru.  
  
> [!WARNING]
>  Pokud chcete upravit souboru .tt prostředky, třeba jako ikony nebo bitové kopie, ujistěte se, zda prostředek jsou zahrnuty v sestavení VSIX. V Průzkumníku řešení, vyberte soubor a zkontrolujte, zda **zahrnout do VSIX** vlastnost je `True`.  
  
 Tento soubor řídí, jak DSL zabalený do Visual Studio integrace rozšíření (VSIX). Další informace najdete v tématu [nasazení řešení jazyk specifické pro doménu](../modeling/deploying-domain-specific-language-solutions.md).  
  
## <a name="see-also"></a>Viz také  
 [Jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md)   
 [Principy modely, třídy a vztahy](../modeling/understanding-models-classes-and-relationships.md)   
 [Přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md)   
 [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)
