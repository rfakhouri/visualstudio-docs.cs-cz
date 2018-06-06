---
title: Navigace v modelu a aktualizace modelu v kódu programu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, programming domain models
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 18f4153db019dd6ded97337d4599f02a6b02ef49
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748931"
---
# <a name="navigate-and-update-a-model-in-program-code"></a>Procházení a aktualizace modelu v programovém kódu

Můžete napsat kód vytvořit a odstranit elementů modelu, nastavit jejich vlastnosti a vytvářet a odstraňovat propojení mezi elementy. Všechny změny, musí být provedeny v rámci transakce. Pokud se elementy jsou zobrazovat v diagramu, diagram bude "vyřešený" automaticky na konci transakce.

## <a name="in-this-topic"></a>V tomto tématu
 [Definici příklad DSL](#example)

 [Navigace modelu](#navigation)

 [Přístup k informacím o – třída](#metadata)

 [Provést změny v transakci](#transaction)

 [Vytváření elementů modelu](#elements)

 [Vytváření odkazů relace](#links)

 [Odstraňování elementy](#deleteelements)

 [Odstranění vztahu odkazy](#deletelinks)

 [Změna pořadí odkazy relace](#reorder)

 [Zámky.](#locks)

 [Kopírování a vkládání](#copy)

 [Navigace a aktualizace diagramy](#diagrams)

 [Přecházení mezi tvary a elementy](#views)

 [Vlastnosti tvarů a konektory](#shapeProperties)

 [DocView a DocData](#docdata)

##  <a name="example"></a> Definici příklad DSL
 Toto je hlavní část DslDefinition.dsl příklady v tomto tématu:

 ![Diagram DSL definice &#45; rodiny stromu modelu](../modeling/media/familyt_person.png)

 Tento model je instance této DSL:

 ![Tudor rodiny stromu modelu](../modeling/media/tudor_familytreemodel.png)

### <a name="references-and-namespaces"></a>Odkazy a obory názvů
 Spustí kód v tomto tématu, by měla odkazovat:

 `Microsoft.VisualStudio.Modeling.Sdk.11.0.dll`

 Váš kód použije tento obor názvů:

 `using Microsoft.VisualStudio.Modeling;`

 Kromě toho pokud píšete kód v na jiný projekt z definovanému vaší DSL, importujte sestavení, které je sestavena Dsl projektu.

##  <a name="navigation"></a> Navigace modelu

### <a name="properties"></a>Vlastnosti
 Vlastnosti domény, které definujete v definici DSL stát vlastnosti, které jsou přístupné v programovém kódu:

 `Person henry = ...;`

 `if (henry.BirthDate < 1500) ...`

 `if (henry.Name.EndsWith("VIII")) ...`

 Pokud chcete nastavit vlastnost, je nutné provést uvnitř [transakce](#transaction):

 `henry.Name = "Henry VIII";`

 Pokud se v k definici DSL se vlastnost **druhu** je **vypočítaná**, nejde ho ale nastavit. Další informace najdete v tématu [vypočítaná a vlastní vlastnosti úložiště](../modeling/calculated-and-custom-storage-properties.md).

### <a name="relationships"></a>Relace
 Vztahy domén, které definujete v definici DSL stát dvojice vlastností, jednu pro třídu na obou koncích relace. Názvy vlastností se zobrazí v diagramu DslDefinition jako popisky na rolích, které na každé straně relace. V závislosti na násobnosti atributu role typ vlastnosti je třída na druhém konci vztahu nebo kolekci této třídy.

 `foreach (Person child in henry.Children) { ... }`

 `FamilyTreeModel ftree = henry.FamilyTreeModel;`

 Vlastnosti v opačné konců relace jsou vždy vzájemné. Po vytvoření nebo odstranění odkaz jsou aktualizovány vlastnosti role na obou elementů. Následující výraz (přípony, který používá `System.Linq`) je vždy hodnotu true pro vztah ParentsHaveChildren v příkladu:

 `(Person p) => p.Children.All(child => child.Parents.Contains(p))`

 `&& p.Parents.All(parent => parent.Children.Contains(p));`

 **ElementLinks**. Relace je také reprezentována modelu prvek s názvem *odkaz*, což je instance typ relace domény. Odkaz má vždy jeden zdroj elementu a element jeden cíl. Tento prvek zdrojový a cílový element může být stejné.

 Odkaz a jeho vlastnosti jsou k dispozici:

 `ParentsHaveChildren link = ParentsHaveChildren.GetLink(henry, edward);`

 `// This is now true:`

 `link == null || link.Parent == henry && link.Child == edward`

 Ve výchozím nastavení je povoleno více než jednu instanci vztahu propojení prvků modelu žádném páru. Ale pokud v definici DSL `Allow Duplicates` příznak platí pro relaci, pak může být více než jeden odkaz a je nutné použít `GetLinks`:

 `foreach (ParentsHaveChildren link in ParentsHaveChildren.GetLinks(henry, edward)) { ... }`

 Existují také další metody pro přístup k odkazy. Příklad:

 `foreach (ParentsHaveChildren link in     ParentsHaveChildren.GetLinksToChildren(henry)) { ... }`

 **Skrytá role.** Pokud v definici DSL **je vlastnost vygenerovat** je **false** pro konkrétní roli, pak vlastnost se vygeneruje odpovídající dané roli. Můžete však stále používat odkazy a procházení odkazů pomocí metody relace:

 `foreach (Person p in ParentsHaveChildren.GetChildren(henry)) { ... }`

 Nejčastěji používaných příkladem je <xref:Microsoft.VisualStudio.Modeling.Diagrams.PresentationViewsSubject> relace, který odkazuje element modelu na tvar, který se zobrazí v diagramu:

 `PresentationViewsSubject.GetPresentation(henry)[0] as PersonShape`

### <a name="the-element-directory"></a>Element adresáře
 Všechny elementy v úložišti pomocí adresáři element se můžete dostat:

 `store.ElementDirectory.AllElements`

 Existují také metody pro vyhledávání elementů, například následující:

 `store.ElementDirectory.FindElements(Person.DomainClassId);`

 `store.ElementDirectory.GetElement(elementId);`

##  <a name="metadata"></a> Přístup k informacím o – třída
 Můžete získat informace o třídy, vztahy a dalších aspektů definici DSL. Příklad:

 `DomainClassInfo personClass = henry.GetDomainClass();`

 `DomainPropertyInfo birthProperty =`

 `personClass.FindDomainProperty("BirthDate")`

 `DomainRelationshipInfo relationship =`

 `link.GetDomainRelationship();`

 `DomainRoleInfo sourceRole = relationship.DomainRole[0];`

 Třídy nadřazenými prvky modelu jsou následující:

-   ModelElement – všechny elementy a vztahy jsou ModelElements

-   ElementLink – všechny vztahy jsou ElementLinks

##  <a name="transaction"></a> Provést změny v transakci
 Vždy, když kód programu změní něco v úložišti, se musí provést v transakci. To platí pro všechny elementy modelu, relace, tvarů, diagramy a jejich vlastnosti. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.Modeling.Transaction>.

 Je nejvhodnější metody řízení transakce s `using` příkaz uzavřena v `try...catch` příkaz:

```
Store store; ...
try
{
  using (Transaction transaction =
    store.TransactionManager.BeginTransaction("update model"))
    // Outermost transaction must always have a name.
  {
    // Make several changes in Store:
    Person p = new Person(store);
    p.FamilyTreeModel = familyTree;
    p.Name = "Edward VI";
    // end of changes to Store

    transaction.Commit(); // Don't forget this!
  } // transaction disposed here
}
catch (Exception ex)
{
  // If an exception occurs, the Store will be
  // rolled back to its previous state.
}
```

 Můžete vytvořit libovolný počet změny v jedné transakci. Můžete otevřít nové transakce uvnitř aktivní transakce.

 Chcete-li provedené změny trvalé, měli byste `Commit` transakce předtím, než je zrušen. Pokud dojde k výjimce, která není zachycena uvnitř transakce, úložišti se resetuje do stavu před změny.

##  <a name="elements"></a> Vytváření elementů modelu
 Tento příklad přidá element do existujícího modelu:

```
FamilyTreeModel familyTree = ...; // The root of the model.
using (Transaction t =
    familyTree.Store.TransactionManager
    .BeginTransaction("update model"))
{
  // Create a new model element
  // in the same partition as the model root:
  Person edward = new Person(familyTree.Partition);
  // Set its embedding relationship:
  edward.FamilyTreeModel = familyTree;
          // same as: familyTree.People.Add(edward);
  // Set its properties:
  edward.Name = "Edward VII";
  t.Commit(); // Don't forget this!
}
```

 Tento příklad znázorňuje tyto základní body o vytváření element:

-   Vytvoření nového elementu v konkrétní oddílu úložiště. Pro prvků modelu a relace, ale není tvarů je to obvykle výchozí oddíl.

-   Díky cílem vnoření relace. Každá osoba DslDefinition tohoto příkladu, musí být cílem relace FamilyTreeHasPeople vkládání. Jak toho docílit, jsme můžete nastavit vlastnost role FamilyTreeModel objektu osoba, nebo přidat osoba, která pro vlastnost role osoby FamilyTreeModel objektu.

-   Nastavit vlastnosti nového elementu, zejména vlastnost, pro který `IsName` DslDefinition platí. Tento příznak označí vlastnost, která slouží k identifikaci element jedinečné v rámci jeho vlastníka. V takovém případě vlastnost Name má tento příznak.

-   Definice DSL tento DSL musí byly načteny do úložiště. Pokud píšete rozšíření třeba příkaz nabídky, obvykle bude již hodnotu true. V ostatních případech můžete explicitně načíst model do úložiště, nebo použít <xref:Microsoft.VisualStudio.Modeling.Integration.ModelBus> se jej načíst. Další informace najdete v tématu [postupy: otevření modelu ze souboru v programovém kódu](../modeling/how-to-open-a-model-from-file-in-program-code.md).

 Když vytvoříte element tímto způsobem, obrazce se automaticky vytvoří (Pokud DSL diagram). Zobrazí se v automaticky přiřazené umístění, s výchozí tvar, barvy a další funkce. Pokud chcete určit, kde a jak se zobrazí související obrazce najdete v tématu [vytváření elementu a jeho tvar](#merge).

##  <a name="links"></a> Vytváření odkazů relace
 Existují dva vztahy definované v příkladu DSL definice. Každý vztah definuje *role vlastnost* u třídy na obou koncích relace.

 Existují tři způsoby, ve kterých můžete vytvořit instance relace. Každá z těchto tří metod má stejný účinek:

-   Nastavte vlastnost přehrávače zdrojové role. Příklad:

    -   `familyTree.People.Add(edward);`

    -   `edward.Parents.Add(henry);`

-   Nastavte vlastnost player role cíl. Příklad:

    -   `edward.familyTreeModel = familyTree;`

         Násobnost této role `1..1`, takže jsme přiřadit hodnotu.

    -   `henry.Children.Add(edward);`

         Násobnost této role `0..*`, takže jsme přidat do kolekce.

-   Vytvořte instanci relace explicitně. Příklad:

    -   `FamilyTreeHasPeople edwardLink = new FamilyTreeHasPeople(familyTreeModel, edward);`

    -   `ParentsHaveChildren edwardHenryLink = new ParentsHaveChildren(henry, edward);`

 Poslední metoda je užitečná, pokud chcete nastavit vlastnosti v relaci sama.

 Když vytvoříte element tímto způsobem, konektor v diagramu se automaticky vytvoří, ale má výchozí tvar, barvu a dalších funkcí. K řízení, jak vytvořit konektor přidružené, najdete v části [vytváření elementu a jeho tvar](#merge).

##  <a name="deleteelements"></a> Odstraňování elementy
 Odstranit element voláním `Delete()`:

 `henry.Delete();`

 Tato operace odstraní také:

-   Vztah odkazy do a z elementu. Například `edward.Parents` už bude obsahovat `henry`.

-   Prvky v rolí, pro které `PropagatesDelete` příznak má hodnotu true. Například obrazec, který zobrazí elementu se odstraní.

 Ve výchozím nastavení, každý vnoření relace má `PropagatesDelete` true v roli cíl. Odstranění `henry` nedojde k odstranění `familyTree`, ale `familyTree.Delete()` by odstranit všechny `Persons`. Další informace najdete v tématu [přizpůsobení chování při odstranění](../modeling/customizing-deletion-behavior.md).

 Ve výchozím nastavení `PropagatesDelete` není pro role referenčních relací na hodnotu true.

 Může způsobit odstranění pravidla vynechat konkrétní šíření při odstraňování objektu. To je užitečné, pokud jsou nahraďte jeden element pro jinou. Můžete zadat jednu nebo více rolí, pro které by neměl být odstranění rozšíří identifikátor GUID. Identifikátor GUID můžete získat z třídy vztahu:

 `henry.Delete(ParentsHaveChildren.SourceDomainRoleId);`

 (Tomto konkrétním příkladu by mít žádný vliv, protože `PropagatesDelete` je `false` pro role `ParentsHaveChildren` vztah.)

 V některých případech odstranění brání existenci zámku na element nebo na element, který by odstranil šíření. Můžete použít `element.CanDelete()` zkontrolujte, zda lze odstranit elementu.

##  <a name="deletelinks"></a> Odstranění vztahu odkazy
 Odebráním element z vlastnosti role můžete odstranit vztah odkaz:

 `henry.Children.Remove(edward); // or:`

 `edward.Parents.Remove(henry);  // or:`

 Můžete také odkaz explicitně odstranit:

 `edwardHenryLink.Delete();`

 Tyto tři metody všechny mají stejný účinek. Stačí použít jeden z nich.

 Pokud má role 0..1 nebo 1..1 násobnost, můžete ho nastavit `null`, nebo s jinou hodnotou:

 `edward.FamilyTreeModel = null;` nebo:

 `edward.FamilyTreeModel = anotherFamilyTree;`

##  <a name="reorder"></a> Znovu řazení odkazy relace
 Odkazy konkrétní relace, které jsou jako zdroj nebo zaměřený na konkrétním modelu element mít konkrétní pořadí. Zobrazí se v pořadí, ve kterém byly přidány. Například tento příkaz předá vždy podřízené objekty ve stejném pořadí:

 `foreach (Person child in henry.Children) ...`

 Můžete změnit pořadí odkazů:

 `ParentsHaveChildren link = GetLink(henry,edward);`

 `ParentsHaveChildren nextLink = GetLink(henry, elizabeth);`

 `DomainRoleInfo role =`

 `link.GetDomainRelationship().DomainRoles[0];`

 `link.MoveBefore(role, nextLink);`

##  <a name="locks"></a> Zámky.
 Změny může být zabránit zámek. Zámky lze nastavit u jednotlivých elementů, u oddílů a v úložišti. Pokud má některé z těchto úrovní zámku, která zabraňuje druh změny, která má být, pokusíte-li ji může být vyvolána výjimka. Je-li zjistit, zda jsou nastaveny zámky pomocí elementu. GetLocks(), což je metody rozšíření, který je definován v oboru názvů <xref:Microsoft.VisualStudio.Modeling.Immutability>.

 Další informace najdete v tématu [definování uzamčení zásad k vytvoření segmenty jen pro čtení](../modeling/defining-a-locking-policy-to-create-read-only-segments.md).

##  <a name="copy"></a> Kopírování a vkládání
 Můžete zkopírovat elementy nebo skupiny elementů <xref:System.Windows.Forms.IDataObject>:

```
Person person = personShape.ModelElement as Person;
Person adopter = adopterShape.ModelElement as Person;
IDataObject data = new DataObject();
personShape.Diagram.ElementOperations
      .Copy(data, person.Children.ToList<ModelElement>());
```

 Elementy jsou uloženy jako skupinu serializovaných elementu.

 Můžete sloučit elementy z objektu IDataObject do modelu:

```
using (Transaction t = targetDiagram.Store.
        TransactionManager.BeginTransaction("paste"))
{
  adopterShape.Diagram.ElementOperations.Merge(adopter, data);
}
```

 `Merge ()` Můžete buď přijmout `PresentationElement` nebo `ModelElement`. Pokud je mu `PresentationElement`, můžete také určit na pozici v diagramu cíl jako třetí parametr.

##  <a name="diagrams"></a> Navigace a aktualizace diagramy
 V DSL element modelu domény, který představuje koncept jako je osoba nebo skladbu, je nezávislý na element tvar, který představuje, najdete v diagramu. Element modelu domény ukládá důležité vlastností a vztahů koncepty. Element tvar ukládá velikost, pozici a barvu zobrazení objektu v diagramu a rozložení jeho součásti.

### <a name="presentation-elements"></a>Prvky prezentace, které
 ![Diagram základní typy elementu a tvar – třída](../modeling/media/dslshapesandelements.png)

 Každý element, který určíte v vaší definice DSL, vytvoří třídu, která je odvozena z jedné z následujících tříd standardní.

|Typ elementu|Base – třída|
|---------------------|----------------|
|Domény – třída|<xref:Microsoft.VisualStudio.Modeling.ModelElement>|
|Relace domény|<xref:Microsoft.VisualStudio.Modeling.ElementLink>|
|Obrazec|<xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape>|
|Konektor|<xref:Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape>|
|diagram|<xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>|

 Element v diagramu obvykle reprezentuje element modelu. Obvykle (ale ne vždy) <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape> představuje instanci třídy domény a <xref:Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape> představuje instanci vztah domény. <xref:Microsoft.VisualStudio.Modeling.Diagrams.PresentationViewsSubject> Vztah odkazuje obrazec nebo odkaz na element modelu, který reprezentuje.

 Každý uzel nebo odkaz tvar patří do jedné diagramu. Obrazec binární propojení připojí dva obrazce uzlu.

 Obrazce mohou mít podřízené tvarů ve dvou sad. Obrazce v `NestedChildShapes` sady se vztahuje pouze na pole ohraničující svého nadřazeného objektu. Obrazce v `RelativeChildShapes` seznamu se mohou objevit mimo nebo částečně mimo hranice nadřazené – například štítek nebo port. Diagram neobsahuje žádné `RelativeChildShapes` a žádné `Parent`.

###  <a name="views"></a> Přecházení mezi tvary a elementy
 Prvky modelu domény a elementy obrazce jsou spojené <xref:Microsoft.VisualStudio.Modeling.Diagrams.PresentationViewsSubject> vztah.

```csharp
// using Microsoft.VisualStudio.Modeling;
// using Microsoft.VisualStudio.Modeling.Diagrams;
// using System.Linq;
Person henry = ...;
PersonShape henryShape =
  PresentationViewsSubject.GetPresentation(henry)
    .FirstOrDefault() as PersonShape;
```

 Stejný vztah obsahuje vztahy odkazy na spojnice v diagramu:

```
Descendants link = Descendants.GetLink(henry, edward);
DescendantConnector dc =
   PresentationViewsSubject.GetPresentation(link)
     .FirstOrDefault() as DescendantConnector;
// dc.FromShape == henryShape && dc.ToShape == edwardShape
```

 Tento vztah obsahuje kořen modelu také odkazy na diagramu:

```
FamilyTreeDiagram diagram =
   PresentationViewsSubject.GetPresentation(familyTree)
      .FirstOrDefault() as FamilyTreeDiagram;
```

 Element modelu reprezentována obrazce, použijte:

 `henryShape.ModelElement as Person`

 `diagram.ModelElement as FamilyTreeModel`

### <a name="navigating-around-the-diagram"></a>Navigace na obrázku
 Obecně není vhodné umožňují přecházet mezi jednotlivými tvarů a konektory v diagramu. Je lepší procházení vztahů v modelu přesun mezi tvarů a konektory jenom v případě, že je nezbytné pro práci na vzhled diagramu. Tyto metody propojit obrazce na obou koncích konektory:

 `personShape.FromRoleLinkShapes, personShape.ToRoleLinkShapes`

 `connector.FromShape, connector.ToShape`

 Mnoho obrazců je složený; jsou vytvořeny nadřazené obrazce a jednu nebo více vrstev podřízených prvků. Obrazce, které jsou umístěny vzhledem ke jiného obrazce jsou označeny jako jeho *podřízené objekty*. Pokud se přesune do nadřazeného obrazce, podřízených přesune s ním.

 *Relativní podřízené* může vyskytovat mimo pole ohraničující nadřazené tvaru. *Vnořené* podřízené objekty zobrazí výhradně uvnitř hranice nadřazeného objektu.

 K získání top sadu tvarů v diagramu, použijte:

 `Diagram.NestedChildShapes`

 Nadřazené třídy tvarů a konektory jsou:

 <xref:Microsoft.VisualStudio.Modeling.ModelElement>

 -- <xref:Microsoft.VisualStudio.Modeling.Diagrams.PresentationElement>

 -- <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement>

 ----- <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape>

 ------- <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>

 ------- *YourShape*

 ----- <xref:Microsoft.VisualStudio.Modeling.Diagrams.LinkShape>

 ------- <xref:Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape>

 --------- *YourConnector*

###  <a name="shapeProperties"></a> Vlastnosti tvarů a konektory
 Ve většině případů není nutné vytvářet explicitní změny do tvarů. Pokud jste změnili elementů modelu, aktualizovat pravidla "oprava" tvarů a konektory. Další informace najdete v tématu [reakce na a šíření změny](../modeling/responding-to-and-propagating-changes.md).

 Je však vhodné změnit některé explicitní obrazce v vlastnosti, které jsou nezávislé na prvků modelu. Můžete například změnit tyto vlastnosti:

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape.Size%2A> -Určuje výšku a šířku tvaru.

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape.Location%2A> -pozice relativně k nadřazené tvar nebo diagram

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.StyleSet%2A> -sadu pera a používá pro kreslení obrazce nebo konektor štětce

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.Hide%2A> – Umožňuje neviditelná tvaru

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.Show%2A> -zviditelní tvaru po `Hide()`

###  <a name="merge"></a> Vytváření elementu a jeho obrazce
 Při vytváření element a propojit jej do stromu vztahů vnoření, obrazce je automaticky vytvořen a s ním spojená. K tomu je potřeba "Opravit" pravidla, které jsou spouštěny na konci transakce. Ale tvar, který se zobrazí v umístění automaticky přiřazeny a jeho tvar, barvu a další funkce, bude mít výchozí hodnoty. Můžete určit, jak je vytvářet tvaru, můžete použít funkci sloučení. Musíte nejprve přidat prvky, které chcete přidat do ElementGroup a pak sloučit skupiny do diagramu.

 Tato metoda:

-   Nastaví název, pokud jste přiřadili vlastnost jako název elementu.

-   Zaznamenává všechny Element sloučení direktivy, který jste zadali v definici DSL.

 Tento příklad vytvoří obrazce na pozici myši při poklepání diagramu. V definici DSL Tato ukázka `FillColor` vlastnost `ExampleShape` má byly vystavené.

```

using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;
partial class MyDiagram
{
  public override void OnDoubleClick(DiagramPointEventArgs e)
  {
    base.OnDoubleClick(e);

    using (Transaction t = this.Store.TransactionManager
        .BeginTransaction("double click"))
    {
      ExampleElement element = new ExampleElement(this.Store);
      ElementGroup group = new ElementGroup(element);

      { // To use a shape of a default size and color, omit this block.
        ExampleShape shape = new ExampleShape(this.Partition);
        shape.ModelElement = element;
        shape.AbsoluteBounds = new RectangleD(0, 0, 1.5, 1.0);
        shape.FillColor = System.Drawing.Color.Azure;
        group.Add(shape);
      }

      this.ElementOperations.MergeElementGroupPrototype(
        this,
        group.CreatePrototype(),
        PointD.ToPointF(e.MousePosition));
      t.Commit();
    }
  }
}

```

 Pokud zadáte více než jeden tvar, nastavit jejich relativní umístění pomocí `AbsoluteBounds`.

 Můžete také nastavit, barvu a dalších vystavené vlastnosti konektorů pomocí této metody.

### <a name="use-transactions"></a>Použití transakcí
 Tvary, konektory a diagramy jsou podtypů <xref:Microsoft.VisualStudio.Modeling.ModelElement> a za provozu v úložišti. Proto musí měnit jim pouze uvnitř transakce. Další informace najdete v tématu [postupy: použití transakcí k aktualizaci modelu](../modeling/how-to-use-transactions-to-update-the-model.md).

##  <a name="docdata"></a> Zobrazení dokumentů a dat dokumentu
 ![Třída diagram diagram standardní typy](../modeling/media/dsldiagramsanddocs.png)

## <a name="store-partitions"></a>Oddíly úložiště
 Při načítání modelu doprovodné diagramu je načten ve stejnou dobu. Obvykle modelu je načten do Store.DefaultPartition a diagram obsahu je načten do druhý oddíl. Obsah každý oddíl jsou obvykle načíst a uložit do samostatného souboru.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Modeling.ModelElement>
- [Ověřování v jazyce specifickém pro doménu](../modeling/validation-in-a-domain-specific-language.md)
- [Vytváření kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md)
- [Postupy: Používání transakcí k aktualizaci modelu](../modeling/how-to-use-transactions-to-update-the-model.md)
- [Integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md)
- [Reagování na změny a šíření změn](../modeling/responding-to-and-propagating-changes.md)
