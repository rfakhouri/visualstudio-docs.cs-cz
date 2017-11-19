---
title: "Přizpůsobení nástrojů a sady nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.selectiondialog
- vs.dsltools.dsldesigner.selecticondialog
- vs.dsltools.dsldesigner.selectcursordialog
helpviewer_keywords: Domain-Specific Language, toolbox
ms.assetid: 2a0d03d7-ebc6-4458-b9f4-d2cb8418a62d
caps.latest.revision: "26"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: f7499aba9d7458ca1bf834bb168a25c6a6ae9b5c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="customizing-tools-and-the-toolbox"></a>Přizpůsobení nástrojů a panelu nástrojů
Je nutné zadat položek sady nástrojů pro prvky, které chcete, aby mohli uživatelé přidat do jejich modely. Existují dva typy nástrojů: element nástroje a nástroje pro připojení. V Návrháři generovaného uživatele můžete vybrat nástroj na element přetáhněte obrazců do diagramu a můžete vybrat nástroj pro připojení k vykreslení odkazy mezi obrazce. Obecně platí nástroje pro element uživatelům přidání instancí třídy domény do jejich modely a nástroje připojení k zajištění jejich přidání instancí vztahů mezi doménami.  
  
 V tomto tématu:  
  
-   [Jak je definována v panelu nástrojů](#ToolboxDef)  
  
-   [Přizpůsobení nástroje – Element](#customizing)  
  
-   [Vytváření skupin elementů z nástroje](#groups)  
  
-   [Přizpůsobení nástroje připojení k](#connections)  
  
##  <a name="ToolboxDef"></a>Jak je definována v panelu nástrojů  
 V Průzkumníku DSL rozbalte uzel Editor a jeho podřízené uzly. Obvykle se zobrazí hierarchie, která vypadá takto:  
  
```  
  
Editor  
     Toobox Tabs  
        MyDsl          //a tab  
           Tools  
               ExampleElement      // an element tool  
               ExampleRelationship // a connection tool  
  
```  
  
 V této části Průzkumník DSL můžete:  
  
-   Vytvořte nové karty. Karty definovat záhlaví části v panelu nástrojů.  
  
-   Vytvořte nové nástroje.  
  
-   Zkopírujte a vložte nástroje.  
  
-   Přesuňte nástroje nahoru nebo dolů v seznamu.  
  
-   Odstraňte karty a nástroje.  
  
> [!IMPORTANT]
>  Chcete-li přidat nebo vložit položky v Průzkumníku DSL, klikněte pravým tlačítkem na nadřazený nového uzlu. Například pokud chcete přidat nástroj, pravým tlačítkem na kartu a ne **nástroje** uzlu. Chcete-li přidat na kartě, klikněte pravým tlačítkem **Editor** uzlu.  
  
 **Ikonu panelu nástrojů** odkazuje vlastnost nástroje pro každý soubor rastrového obrázku velikosti 16 x 16. Tyto soubory jsou obvykle zachovány v **Dsl\Resources** složky.  
  
 **Třída** vlastnost nástroj na element odkazuje na třídu konkrétní domény. Ve výchozím nastavení nástroj vytvoří instance této třídy. Však můžete napsat kód tak, aby měl nástroj pro vytváření skupin elementy nebo elementy různých typů.  
  
 **Připojení Tvůrce** odkazuje vlastnost nástroje pro připojení na připojení tvůrce, který definuje, jaké typy elementů nástroj může připojit, a jaké vztahy vytvoří mezi nimi. Připojení počítačů jsou definovány jako uzly v Průzkumníku DSL. Připojení počítačů se vytvoří automaticky při definování vztahů mezi doménami, ale můžete napsat kód se přizpůsobit.  
  
#### <a name="to-add-a-tool-to-the-toolbox"></a>Chcete-li přidat nástroj do sady nástrojů  
  
1.  Obvykle vytvoříte nástroj na element po vytvoření třídy tvar a mapovat na třídy domény.  
  
     Obvykle vytvoříte konektor nástroj po vytvoření třída konektoru a mapovat na referenční vztah.  
  
2.  V Průzkumníku DSL rozbalte **Editor** uzlu a **sada nástrojů karty** uzlu.  
  
     Klikněte pravým tlačítkem na uzel karta sada nástrojů a pak klikněte na **přidejte nový Element nástroj** nebo **přidat nový nástroj pro připojení**.  
  
3.  Nastavte **ikonu panelu nástrojů** vlastnost odkazovat na rastr o velikosti 16 x 16.  
  
     Pokud chcete definovat novou ikonu, vytvořte soubor rastrového obrázku v Průzkumníku řešení ve **Dsl\Resources** složky. Soubor by měl mít následující hodnoty vlastností: **akce sestavení** = **obsahu**; **Kopírovat do výstupního adresáře** = **nekopírovat**.  
  
4.  **Pro nástroj na element:** nastavit **třída** vlastnost nástroje k odkazování na třídu konkrétní domény, který je namapovaný na obrazce.  
  
     **Pro nástroj konektor:** nastavit **připojení Tvůrce** vlastnost nástroje k jedné z položek, které jsou nabízena v rozevíracím seznamu. Připojení počítačů se automaticky vytvoří při mapování konektor relaci domény. Pokud jste nedávno vytvořili konektor, vyberete by za normálních okolností Tvůrce přidružené připojení.  
  
5.  Chcete-li otestovat DSL, stiskněte klávesu F5 nebo CTRL + F5 a experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otevřete soubor modelu ukázka. Nový nástroj by se zobrazit na panelu nástrojů. Přetáhněte ji na diagramu na zkontrolujte, že vytváří nového elementu.  
  
     Pokud nástroj nezobrazí, zastavte experimentální [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. V systému Windows **spustit** nabídce Spustit **resetovat instanci Microsoft Visual Studio 2010 experimentální**. Na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**. Pak vyzkoušejte DSL znovu.  
  
##  <a name="customizing"></a>Přizpůsobení nástroje – Element  
 Ve výchozím nastavení nástroj vytvoří jednu instanci zadané třídy, ale může to lišit dvěma způsoby:  
  
-   Definujte Element sloučení direktivy jiné třídy, tím jim umožníte přijímat nové instance této třídy a tím jim umožníte vytvořit další odkazy, při vytváření nového elementu. Například může povolit uživatelům vyřadit komentář na jiný element a tak vytvářet použití odkazu mezi nimi.  
  
     Tato vlastní nastavení také ovlivňuje, co se stane, když uživatel vloží nebo nastavuje tažením a zahodí element.  
  
     Další informace najdete v tématu [přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md).  
  
-   Napište kód pro přizpůsobit nástroj tak, aby ji můžete vytvořit skupiny elementů. Tento nástroj se inicializuje pomocí metody v ToolboxHelper.cs, který můžete přepsat. Další informace najdete v tématu [vytváření skupin z elementy z nástroje](#groups).  
  
##  <a name="groups"></a>Vytváření skupin elementů z nástroje  
 Každý element nástroj obsahuje prototyp prvky, které by měl být vytvořen. Ve výchozím nastavení každý element nástroj vytvoří jeden prvek, ale je také možné vytvořit skupinu souvisejících objektů, které se nástroj. K tomuto účelu inicializaci nástroje s <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype> obsahující související položky.  
  
 Následující příklad je převzat ze DSL, ve kterém je typ tranzistorové. Každý tranzistorové má tři pojmenované terminály. Nástroj element pro tranzistory ukládá prototyp obsahující čtyři prvků modelu a tři vztah odkazy. Když uživatel nastavuje tažením nástroj do diagramu, prototyp je vytvořena instance a propojí s kořenem modelu.  
  
 Tento kód přepíše metodu, která je definována v **Dsl\GeneratedCode\ToolboxHelper.cs**.  
  
 Další informace o přizpůsobení modelu pomocí programu kódu najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
  public partial class CircuitsToolboxHelper  
  {  
    /// <summary>  
    /// Toolbox initialization, called for each element tool on the toolbox.  
    /// This version deals with each Component subtype separately.  
    /// </summary>  
    /// <param name="store"></param>  
    /// <param name="domainClassId">Identifies the domain class this tool should instantiate.</param>  
    /// <returns>prototype of the object or group of objects to be created by tool</returns>  
    protected override ElementGroupPrototype CreateElementToolPrototype(Store store, Guid domainClassId)  
    {  
        if (domainClassId == Transistor.DomainClassId)  
        {  
            Transistor transistor = new Transistor(store);  
  
            transistor.Base = new ComponentTerminal(store);  
            transistor.Collector = new ComponentTerminal(store);  
            transistor.Emitter = new ComponentTerminal(store);  
  
            transistor.Base.Name = "base";  
            transistor.Collector.Name = "collector";  
            transistor.Emitter.Name = "emitter";  
  
            // Create an ElementGroup for the Toolbox.  
            ElementGroup elementGroup = new ElementGroup(store.DefaultPartition);  
            elementGroup.AddGraph(transistor, true);  
            // AddGraph includes the embedded parts  
  
            return elementGroup.CreatePrototype();  
        }  
        else  
        {  
            return base.CreateElementToolPrototype(store, domainClassId);  
}  }    }  
  
```  
  
##  <a name="connections"></a>Přizpůsobení nástroje připojení k  
 Obvykle můžete vytvořit nástroj na element, když vytvoříte novou třídu konektor. Alternativně můžete použít přetížení nástroj tím, že se typy dva elementy end určit typ vztahu. Můžete třeba definovat připojení nástroj, který může vytvořit osoba osoba vztahy a vztahy městě osoby.  
  
 Vyvolání nástroje připojení k připojení počítačů. Použijte připojení počítačů k určení, jak mohou uživatelé propojení prvků v Návrháři vygenerovaný. Připojení počítačů zadejte prvky, které lze propojit a druh odkazu, který se vytvoří mezi nimi.  
  
 Když vytvoříte referenční vztah mezi třídami domény, se automaticky vytvoří Tvůrce připojení. Tohoto Tvůrce připojení můžete použít při mapování nástroj pro připojení. Další informace o tom, jak vytvořit připojení nástrojů najdete v tématu [konfigurace sady nástrojů](../modeling/customizing-tools-and-the-toolbox.md).  
  
 Tvůrce výchozí připojení můžete upravit tak, aby ho řeší jiný rozsah zdrojové a cílové typů a vytvořit různé typy relace.  
  
 Také můžete psát vlastní kód pro připojení počítačů k zadejte zdrojové a cílové třídy pro připojení, definování typu navázání a ním provádět jiné akce přidružené k vytvoření připojení.  
  
### <a name="the-structure-of-connection-builders"></a>Struktura připojení počítačů  
 Připojení počítačů obsahovat jednu nebo více odkaz připojit direktivy, které určují relace domény a zdrojové a cílové elementy. V šabloně řešení tok úkolů, například se zobrazí **CommentReferencesSubjectsBuilder** v **DSL Explorer**. Toto připojení tvůrce obsahuje jeden odkaz připojení s názvem direktiva **CommentReferencesSubjects – odkazová**, která se mapuje na relace domény **CommentReferencesSubjects – odkazová**. Připojit tento odkaz direktiva obsahuje direktivu role zdroj, který odkazuje na `Comment` domény třídy a direktivu role cíl, který odkazuje na `FlowElement` třída domény.  
  
### <a name="using-connection-builders-to-restrict-source-and-target-roles"></a>Pomocí připojení počítačů k omezení zdrojové a cílové role  
 Připojení počítačů můžete omezit výskyt určité třídy v zdrojovou roli nebo roli cíl vztahu zadané doméně. Například můžete mít základní doménu třídu, která má vztah k jiné třídě domény domény, ale nebudete chtít všechny odvozené třídy základní třídy tak, aby měl stejné role v této relaci. V řešení tok úkolů jsou čtyři třídy konkrétní domény (**StartPoint**, **koncový bod**, **MergeBranch**, a **synchronizace**), přímo domény abstraktní třídy dědí **FlowElement**, a dva konkrétní domény třídy (**úloh** a **ObjectInState**), dědí nepřímo. K dispozici je také **toku** referenční vztah, který přebírá **FlowElement** třídy domény v jeho roli zdroj i cíl role. Však instanci **koncový bod** třída domény by neměl být zdroji instance **toku** vztah, ani by měl instanci **StartPoint** třídu mít cílové instance **toku** vztah. **FlowBuilder** Tvůrce připojení má odkaz připojení s názvem direktiva **toku** určující, které třídy domény můžete přehrát zdrojovou roli (**úloh**,  **MergeBranch**, **StartPoint**, a **synchronizace**) a který můžete přehrát target role (**MergeBranch**,  **Koncový bod**, a **synchronizace**).  
  
### <a name="connection-builders-with-multiple-link-connect-directives"></a>Připojení počítačů s více odkaz připojit direktivy  
 Můžete přidat více než jeden odkaz připojit – direktiva Tvůrce připojení. To vám může pomoct skrýt některé složitosti modelu domény od uživatelů a zachovat **sada nástrojů** zahlcen příliš. Můžete přidat odkaz připojit direktivy pro několik relace jinou doménu k Tvůrce jednoho připojení. Ale doporučujeme, abyste zkombinovali vztahy domén při vykonávání přibližně stejnou funkci.  
  
 V řešení tok úkolů **toku** nástroj pro připojení slouží k vykreslení instance i **toku** a **Tok_objektů** vztahy domén. **FlowBuilder** Tvůrce připojení musí, kromě **toku** odkaz připojit – direktiva dříve popisované, dvě odkaz připojení s názvem direktivy **Tok_objektů**. Tyto direktivy určit, že instance **Tok_objektů** vztah může být vykreslován mezi instancemi **ObjectInState** třídy domény, nebo z instance systému **ObjectInState**  do instance **úloh**, ale není mezi dvěma instancemi **úloh**, nebo z instance systému **úloh** na instanci **ObjectInState**. Ale instance **toku** vztah může být vykreslován mezi dvěma instancemi **úloh**. Pokud zkompilování a spuštění řešení tok úkolů, zobrazí se tento kreslení **toku** z instance systému **ObjectInState** do instance **úloh** vytvoří instanci **Tok_objektů**, ale vykreslování **toku** mezi dvěma instancemi **úloh** vytvoří instanci **toku**.  
  
### <a name="custom-code-for-connection-builders"></a>Vlastní kód pro připojení počítačů  
 Existují čtyři políček v uživatelském rozhraní, které určují různé typy přizpůsobení připojení počítačů:  
  
-   **přijmout vlastní** políčko direktivu zdrojová nebo cílová role  
  
-   **vlastní připojení** políčko direktivu zdrojová nebo cílová role  
  
-   **používá vlastní připojení** políčko direktivu connect  
  
-   **je vlastní** vlastnost Tvůrce připojení  
  
 Je nutné zadat kód programu, který toto vlastní nastavení. Pokud chcete zjistit, jaké kódu, je nutné zadat, zkontrolujte jednu z těchto polí, klikněte na tlačítko transformaci všech šablon a následně vytvořit řešení. Zpráva o chybě, bude. Dvakrát klikněte na zprávu o chybách zobrazíte komentář, který vysvětluje, co kód, že měli byste přidat.  
  
> [!NOTE]
>  Pokud chcete přidat vlastní kód, vytvoření částečné třídy definice v souboru kódu odděleně od kódu soubory ve složkách GeneratedCode. Aby nedošlo ke ztrátě práci, byste neměli upravovat soubory generovaného kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).  
  
#### <a name="creating-custom-connection-code"></a>Vytvoření připojení vlastní kód  
 V každé propojení připojit – direktiva, **zdroje role direktivy** kartě definuje, co jste typy můžete přetáhnout. Podobně **cíle role direktivy** kartě definuje pro co typy, které můžete přetáhnout. U každého typu můžete dále určit, jestli se má povolit připojení (pro tento odkaz připojit – direktiva) nastavením **přijmout vlastní** příznak a pak poskytuje další kód.  
  
 Můžete také upravit, co se stane, když je vytvořeno připojení. Například můžete přizpůsobit jenom v případě, kde dojde k přetáhněte do nebo z určité třídy, připojit tento jeden odkaz všechny případy – direktiva řídí, nebo celý Tvůrce FlowBuilder připojení. Pro každou z těchto možností můžete nastavit vlastní příznaky na příslušné úrovni. Proveďte transformaci všech šablon a pokuste se sestavte řešení, chybové zprávy vás nasměrovat k komentáře, které jsou v generovaného kódu. Tyto komentáře zjistit, co je třeba zadat.  
  
 V ukázce Diagram součásti Tvůrce připojení pro připojení relace domény upravit tak, aby omezení připojení, které můžete provedeny mezi porty. Následující obrázek znázorňuje, abyste vytvořili připojení pouze z `OutPort` elementů `InPort` elementů, ale lze vnořit součásti uvnitř sebe navzájem.  
  
 **Připojení přicházejících na OutPort z vnořené součásti**  
  
 ![Tvůrce připojení](../modeling/media/connectionbuilder_3.png "ConnectionBuilder_3")  
  
 Proto můžete zadat, že připojení mohou pocházet z vnořených součástí do OutPort. Pokud chcete zadat toto připojení, můžete nastavit **používá vlastní přijmout** na **InPort** typ jako zdrojovou roli a **OutPort** jako cíl role v typu **DSL podrobnosti**  okno, jak je znázorněno na následujícím obrázku:  
  
 **Odkaz připojit v Průzkumníku DSL – direktiva**  
  
 ![Obrázek připojení Tvůrce](../modeling/media/connectionbuilder_4a.png "ConnectionBuilder_4a")  
  
 **Odkaz připojit – direktiva v okně podrobností DSL**  
  
 ![](../modeling/media/connectionbuilder_4b.png "ConnectionBuilder_4b")  
  
 Pak je nutné zadat metody ve třídě ConnectionBuilder:  
  
```  
  public partial class ConnectionBuilder  
  {  
    /// <summary>  
    /// OK if this component has children  
    /// </summary>  
    private static bool CanAcceptInPortAsSource(InPort candidate)  
    {  
       return candidate.Component.Children.Count > 0;  
    }  
  
    /// <summary>  
    /// Only if source is on parent of target.  
    /// </summary>  
    private static bool CanAcceptInPortAndInPortAsSourceAndTarget                (InPort sourceInPort, InPort targetInPort)  
    {  
      return sourceInPort.Component == targetInPort.Component.Parent;  
    }  
// And similar for OutPorts...  
```  
  
 Další informace o přizpůsobení modelu pomocí programu kódu najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 Podobný kód, můžete použít například uživatelům zabránit ve vytváření smyčky s odkazy nadřazený podřízený. Tato omezení jsou považovány za "pevné, omezení, protože uživatelé nelze poruší kdykoli. Můžete také vytvořit "soft" ověřovací kontroly, které uživatelé mohou obejít dočasně vytvořením neplatná konfigurace, které nebudou ji moct uložit.  
  
### <a name="good-practice-in-defining-connection-builders"></a>Vhodné k definování připojení počítačů  
 Měli byste jeden Tvůrce připojení vytvořit různé typy vztahů pouze v případě, že se koncepčně vztahují. V ukázce tok úkolů použijete k vytvoření toků mezi úkoly a také mezi úlohy a objekty stejné Tvůrce. Ale by bylo matoucí pomocí stejné Tvůrce vytvářet vztahy mezi komentáře a úlohy.  
  
 Pokud definujete Tvůrce připojení pro více typů vztahů, se ujistěte, že nesmí se shodovat více než jeden typ ze stejného páru zdrojové a cílové objekty. Výsledky, jinak nepředvídatelné.  
  
 Použít vlastní kód použít, pevné' omezení, ale měli byste zvážit, zda by měl mít uživatelé dočasně provádět neplatný připojení. Pokud by měly, můžete upravit omezení, aby připojení nejsou ověřit, dokud uživatelé se pokusí uložit změny.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md)   
 [Kopírování chování přizpůsobení](../modeling/customizing-copy-behavior.md)   
 [Postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Ukázka diagramy okruh DSL](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)