---
title: Přizpůsobení map kódu úpravou souborů DGML
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency graphs, creating path aliases
- dependency graphs, linking items to nodes
- graph documents, creating path aliases
- dependency graphs, grouping nodes
- graph documents, editing
- graph documents, linking items to nodes
- graph documents, customizing
- graph documentings, assigning categories and properties
- dependency graphs, editing
- dependency graphs, customizing
- graph documents, grouping nodes
- dependency graphs, assigning categories and properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7ee92121e57b7c3f6391d290ff0c5fde0d689e3c
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="customize-code-maps-by-editing-the-dgml-files"></a>Přizpůsobení map kódu úpravou souborů DGML
Chcete-li přizpůsobit Mapa kódu, můžete upravit soubor směrované grafu Markup Language (.dgml) mapy. Například můžete upravit prvky k určení vlastních stylů, kategorií a vlastností elementy kódu a odkazy, nebo odkaz dokumenty nebo přiřadit adresy URL elementy kódu nebo odkazy. Další informace o DGML elementy najdete v tématu [odkaz směrované grafů Markup Language (DGML)](../modeling/directed-graph-markup-language-dgml-reference.md).

 Upravte soubor .dgml Mapa kódu v textovém editoru nebo editoru XML. Pokud mapy je součástí řešení sady Visual Studio, vyberte ho v **Průzkumníku řešení**, otevřete místní nabídku a vyberte **otevřete s**, **editoru XML (Text)**.

> [!NOTE]
>  Pokud chcete vytvořit map kódu, musí mít Visual Studio Enterprise. Pokud upravujete Mapa kódu v sadě Visual Studio, ho vyčistí všechny nepoužívané DGML elementy a atributy odstraněním je při uložení souboru .dgml. Vytvoří také elementy kódu automaticky při ručně přidáte nové odkazy. Při ukládání souboru .dgml mohou být všechny atributy, které byly přidány do prvku, uspořádány podle abecedy.

##  <a name="OrganizeNodes"></a> Elementy kódu skupiny
 Můžete přidat nové skupiny nebo převést stávající uzly do skupiny.

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Chcete-li převést element kódu do skupiny, vyhledejte `<Node/>` element pro tento element kódu.

     \- nebo –

     Chcete-li přidat novou skupinu, vyhledejte `<Nodes>` části. Přidejte nový `<Node/>` elementu.

3.  V `<Node/>` elementu, přidejte `Group` atribut k určení, zda daná skupina zobrazovat jako rozbalit nebo sbalit. Příklad:

    ```xml
    <Nodes>
       <Node Id="MyFirstGroup" Group="Expanded" />
       <Node Id="MySecondGroup" Group="Collapsed" />
    </Nodes>
    ```

4.  V `<Links>` část, ujistěte se, že `<Link/>` element, který má následující atributy existují pro každý vztah mezi element kódu skupiny a její podřízené elementy kódu:

    -   A `Source` atribut, který určuje elementu skupiny kódu

    -   A `Target` atribut, který určuje podřízený element kódu

    -   A `Category` atribut, který určuje `Contains` vztah mezi elementu skupiny kódu a jeho podřízený element kódu

     Příklad:

    ```xml
    <Links>
       <Link Category="Contains" Source="MyFirstNewGroup" Target="FirstGroupChildOne" />
       <Link Category ="Contains" Source="MyFirstNewGroup" Target="FirstGroupChildTwo" />
       <Link Category ="Contains" Source="MySecondNewGroup" Target="SecondGroupChildOne" />
       <Link Category="Contains" Source="MySecondNewGroup" Target="SecondGroupChildTwo" />
    </Links>
    ```

     Další informace o `Category` atributů najdete v tématu [kategorie přiřadit elementy kódu a odkazy](#AssignCategories).

##  <a name="ChangeGraphStyle"></a> Umožňuje změnit styl mapy
 Barva pozadí a barvu ohraničení mapy můžete změnit úpravou souboru .dgml mapy. Chcete-li změnit styl elementy kódu a odkazy, [změnit styl elementy kódu a odkazy](#Highlight).

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  V `<DirectedGraph>` elementu přidat kterýkoliv z následujících atributů změnit jeho styl:

     Barvu pozadí

    ```xml
    Background="ColorNameOrHexadecimalValue"
    ```

     Barvu ohraničení

    ```xml
    Stroke="StrokeValue"
    ```

     Příklad:

    ```xml
    <DirectedGraph Background="Green" xmlns="http://schemas.microsoft.com/vs/2009/dgml" >
       ...
       ...
    </DirectedGraph>
    ```

##  <a name="Highlight"></a> Umožňuje změnit styl elementy kódu a odkazy

###  <a name="CreateCustomStyles"></a>
 Vlastní styly můžete aplikovat na následující elementy kódu:

-   Elementy jednoho kódu a odkazy

-   Skupiny elementy kódu a odkazy

-   Skupiny elementy kódu a odkazy na základě určitých podmínek

> [!TIP]
>  Pokud máte opakující se styly napříč mnoha elementy kódu nebo odkazy, zvažte použití kategorii pro tyto elementy kódu nebo odkazy a potom se použijí styl do této kategorie spadají. Další informace najdete v tématu [přiřadit kategorie pro elementy kódu a odkazy](#AssignCategories) a [přiřadit vlastností elementy kódu a odkazy](#AssignProperties).

##### <a name="to-apply-a-custom-style-to-a-single-code-element"></a>Pokud chcete použít vlastní styl na element jednoho kódu

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Najít element kódu `<Node/>` elementu. Přidáte některou z těchto atributů k přizpůsobení jeho styl:

     Barvu pozadí

    ```xml
    Background="ColorNameOrHexadecimalValue"
    ```

     Obrys

    ```xml
    Stroke="ColorNameOrHexadecimalValue"
    ```

     Tloušťka obrysu

    ```xml
    StrokeThickness="StrokeValue"
    ```

     Barva textu

    ```xml
    Foreground="ColorNameOrHexadecimalValue"
    ```

     Ikona

    ```xml
    Icon="IconFilePathLocation"
    ```

     Velikost textu

    ```xml
    FontSize="FontSizeValue"
    ```

     Typ textu

    ```xml
    FontFamily="FontFamilyName"
    ```

     Tloušťka textu

    ```xml
    FontWeight="FontWeightValue"
    ```

     Styl textu

    ```xml
    FontStyle="FontStyleName"
    ```

     Například můžete zadat `Italic` jako styl textu.

     Textura

    ```xml
    Style="Glass"
    ```

     - nebo –

    ```xml
    Style="Plain"
    ```

     Obrazec

     Pokud chcete nahradit tvaru ikonu, nastavte `Shape` vlastnost `None` a nastavte `Icon` vlastnost k cestě se soubor ikony.

    ```xml
    Shape="ShapeFilePathLocation"
    ```

     Příklad:

    ```xml
    <Nodes>
       <Node Id="MyNode" Background="#FF008000" Stroke="#FF000000"
       Foreground="#FFFFFFFF" Icon="...\Icons\Globe.png"/>
    </Nodes>
    ```

##### <a name="to-apply-a-custom-style-to-a-single-link"></a>Aplikace vlastního stylu na jedno propojení

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Najít `<Link/>` elementu, který obsahuje názvy element kódu zdrojový a cílový element kódu.

3.  V `<Link/>` elementu přidat kterýkoliv z následujících atributů k přizpůsobení jeho styl:

     Barva obrysu a šipky

    ```xml
    Stroke="ColorNameOrHexadecimalValue"
    ```

     Tloušťka obrysu

    ```xml
    StrokeThickness="StrokeValue"
    ```

     Styl obrysu

    ```xml
    StrokeDashArray="StrokeArrayValues"
    ```

     Příklad:

    ```xml
    <Links>
       <Link Source="MyFirstNode" Target="MySecondNode" Background="Green" Stroke="#FF000000" StrokeDashArray="2,2"/>
    </Links>
    ```

##### <a name="to-apply-custom-styles-to-a-group-of-code-elements-or-links"></a>Použít vlastní styly pro skupinu elementy kódu nebo odkazů

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Pokud `<Styles></Styles>` element neexistuje, přidat pod `<DirectedGraph></DirectedGraph>` element po `<Links></Links>` elementu.

3.  V `<Styles></Styles>` element v části `<Style/>` elementu a zadat následující atributy:

    -   `TargetType="Node` &#124; `Link | Graph"`

    -   `GroupLabel="` *NameInLegendBox* `"`

    -   `ValueLabel="` *NameInStylePickerBox* `"`

     Pro použití vlastního stylu na všechny cílové typy nepoužívejte podmínku.

##### <a name="to-apply-a-conditional-style-to-groups-of-code-elements-or-links"></a>Použití podmíněného stylu skupin elementy kódu nebo odkazy

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  V `<Style/>` elementu, přidejte `<Condition/>` elementu, který obsahuje `Expression` atributu zadejte výraz, který vrací logickou hodnotu.

     Příklad:

    ```xml
    <Condition Expression="MyCategory"/>
    ```

     - nebo –

    ```xml
    <Condition Expression="MyCategory > 100"/>
    ```

     - nebo –

    ```xml
    <Condition Expression="HasCategory('MyCategory')"/>
    ```

     Tento výraz používá následující syntaxi BNF (Backus-Naur Form):

     <Expression> ::= <BinaryExpression> &#124; <UnaryExpression> &#124; "("<Expression>")" &#124; <MemberBindings> &#124; <Literal> &#124; <Number>

     <BinaryExpression> ::= <Expression> <Operator> <Expression>

     <UnaryExpression> ::= "!" <Expression> &#124; "+" <Expression> &#124; "-" <Expression>

     <Operator> :: = "<" &#124; "\<=" &#124; "=" &#124; "> =" &#124; ">" &#124; "! =" &#124; "nebo" &#124; "a" &#124; "+" &#124; "*" &#124; "/" &#124; "-"

     <MemberBindings> ::= <MemberBindings> &#124; <MemberBinding> "." <MemberBinding>

     <MemberBinding> ::= <MethodCall> &#124; <PropertyGet>

     <MethodCall> ::= <Identifier> "(" <MethodArgs> ")"

     <PropertyGet> :: = Identifikátor

     <MethodArgs> ::= <Expression> &#124; <Expression> "," <MethodArgs> &#124; <empty>

     <Identifier> ::= [^. ]*

     <Literal> :: = jednoduchá nebo dvojité uvozovky řetězcový literál

     <Number> :: = řetězec číslic potřeby s desetinnou

     Můžete určit více `<Condition/>` prvky, které musí být hodnota true, má-li použít styl.

3.  Na další řádek po `<Condition/>` elementu přidat jeden nebo více `<Setter/>` elementy k určení `Property` atribut a pevná `Value` počítaný nebo atributu `Expression` atribut aplikovat na mapě, elementy kódu nebo odkazy, které splňují Podmínka.

     Příklad:

    ```xml
    <Setter Property="BackGround" Value="Green"/>
    ```

 Jako jednoduchý kompletní příklad, následující podmínka Určuje, že element kódu se zobrazí zelená nebo red podle toho, zda jeho `Passed` kategorie je nastaven na `True` nebo `False`:

```xml
<?xml version="1.0" encoding="utf-8"?>
<DirectedGraph xmlns="http://schemas.microsoft.com/vs/2009/dgml">
   <Nodes>
      <Node Id="MyFirstNode" Passed="True" />
      <Node Id="MySecondNode" Passed="False" />
   </Nodes>
   <Links>
   </Links>
   <Styles>
      <Style TargetType="Node" GroupLabel="Passed" ValueLabel="True">
         <Condition Expression="Passed='True'"/>
         <Setter Property="Background" Value="Green"/>
      </Style>
      <Style TargetType="Node" GroupLabel="Passed" ValueLabel="False">
         <Condition Expression="Passed='False'"/>
         <Setter Property="Background" Value="Red"/>
      </Style>
   </Styles>
</DirectedGraph>
```

 Následující tabulka obsahuje některé ukázkové podmínky, které lze použít:

 Nastavte velikost písma v závislosti na počtu řádků kódu, který také změní velikost elementu kódu. Tento příklad používá jeden výraz podmíněného pro nastavení více vlastností, `FontSize` a `FontFamily`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<DirectedGraph xmlns="http://schemas.microsoft.com/vs/2009/dgml">
<Nodes>
   <Node Id="Class1" LinesOfCode ="200" />
   <Node Id="Class2" LinesOfCode ="1000" />
   <Node Id="Class3" LinesOfCode ="20" />
</Nodes>
<Properties>
   <Property Id="LinesOfCode" Label="LinesOfCode" Description="LinesOfCode" DataType="System.Int32" />
</Properties>
<Styles>
   <Style TargetType="Node" GroupLabel="LinesOfCode" ValueLabel="Function">
      <Condition Expression="LinesOfCode > 0" />
      <Setter Property="FontSize" Expression="Math.Max(9,Math.Sqrt(LinesOfCode))" />
      <Setter Property="FontFamily" Value="Papyrus" />
   </Style>
</Styles>
</DirectedGraph>
```

 Nastavení barvy pozadí elementu kódu na základě `Coverage` vlastnost. Styly jsou vyhodnocovány v pořadí, ve kterém se zobrazují, podobně jako `if-else` příkazy.

 V tomto příkladu:

1.  Pokud `Coverage` > 80, nastavte `Background` vlastnost zeleně.

2.  Pokud jiný `Coverage` > 50, nastavte `Background` vlastnost odstín oranžová založené na hodnotu `Coverage` vlastnost.

3.  Jinak nastavte `Background` vlastnost odstín red podle hodnotu `Coverage` vlastnost.

```xml
<?xml version="1.0" encoding="utf-8"?>
<DirectedGraph xmlns="http://schemas.microsoft.com/vs/2009/dgml">
<Nodes>
   <Node Id="Class1" Coverage="58" />
   <Node Id="Class2" Coverage="95" />
   <Node Id="Class3" Coverage="32" />
</Nodes>
<Properties>
   <Property Id="Coverage" Label="Coverage" Description="Code coverage as a percentage of blocks" DataType="Double" />
</Properties>
<Styles>
   <Style TargetType="Node" GroupLabel="Coverage" ValueLabel="Good">
      <Condition Expression="Coverage > 80" />
      <Setter Property="Background" Value="Green" />
   </Style>
   <Style TargetType="Node" GroupLabel="Coverage" ValueLabel="OK">
      <Condition Expression="Coverage > 50" />
      <Setter Property="Background" Expression="Color.FromRgb(180 * Math.Max(1, (80 - Coverage) / 30), 180, 0)" />
   </Style>
   <Style TargetType="Node" GroupLabel="Coverage" ValueLabel="Bad">
      <Setter Property="Background" Expression="Color.FromRgb(180, 180 * Coverage / 50, 0)" />
   </Style>
</Styles>
</DirectedGraph>
```

 Nastavte `Shape` vlastnost `None` tak, aby na ikonu, nahradí tvaru. Použití `Icon` vlastnosti k určení umístění ikony.

```xml
<DirectedGraph xmlns="http://schemas.microsoft.com/vs/2009/dgml">
<Nodes>
   <Node Id="Automation" Category="Test" Label="Automation" />
   <Node Id="C# Provider" Category="Provider" Label="C# Provider" />
</Nodes>
<Categories>
   <Category Id="Provider" Icon="...\Icons\Module.png" Shape="None" />
   <Category Id="Test" Icon="...\Icons\Page.png" Shape="None" />
</Categories>
<Properties>
   <Property Id="Icon" DataType="System.String" />
   <Property Id="Label" Label="Label" Description="Displayable label of an Annotatable object" DataType="System.String" />
   <Property Id="Shape" DataType="System.String" />
</Properties>
<Styles>
   <Style TargetType="Node" GroupLabel="Group" ValueLabel="Has category">
      <Condition Expression="HasCategory('Group')" />
      <Setter Property="Background" Value="#80008080" />
   </Style>
   <Style TargetType="Node">
      <Setter Property="HorizontalAlignment" Value="Center" />
   </Style>
</Styles>
</DirectedGraph>
```

##  <a name="AssignProperties"></a> Vlastnosti přiřadit elementy kódu a odkazy
 Elementy kódu a odkazy můžete uspořádat přiřazením vlastnosti. Můžete například vybrat elementy kódu, které mají specifické vlastnosti, takže můžete seskupovat je, změnit jejich styl nebo je skrýt.

#### <a name="to-assign-a-property-to-a-code-element"></a>Přiřazení vlastnosti na element kódu

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Najít `<Node/>` element pro tento element kódu. Zadejte název vlastnosti a jeho hodnotu. Příklad:

    ```xml
    <Nodes>
       <Node Id="MyNode" MyPropertyName="PropertyValue" />
    </Nodes>
    ```

3.  Přidat `<Property/>` elementu, který chcete `<Properties>` části zadejte atributy, jako je například viditelné název a datový typ:

    ```xml
    <Properties>
       <Property Id="MyPropertyName" Label="My Property" DataType="System.DataType"/>
    </Properties>
    ```

#### <a name="to-assign-a-property-to-a-link"></a>Přiřazení vlastnosti propojení

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Najít `<Link/>` elementu, který obsahuje názvy element kódu zdrojový a cílový element kódu.

3.  V `<Node/>` elementu, zadejte název vlastnosti a jeho hodnotu. Příklad:

    ```xml
    <Links>
       <Link Source="MyFirstNode" Target="MySecondNode" MyPropertyName="PropertyValue" />
    </Links>
    ```

4.  Přidat `<Property/>` elementu, který chcete `<Properties>` části zadejte atributy, jako je například viditelné název a datový typ:

    ```xml
    <Properties>
       <Property Id="MyPropertyName" Label="My Property Name" DataType="System.DataType"/>
    </Properties>
    ```

##  <a name="AssignCategories"></a> Přiřaďte kategorie k elementy kódu a odkazy
 Následující části ukazují, jak můžete uspořádat elementy kódu přiřazením kategorií a jak můžete vytvořit hierarchické kategorií, které vám pomůžou uspořádání elementy kódu a přidání atributů do kategorií podřízené s použitím dědičnosti.

#### <a name="to-assign-a-category-to-a-code-element"></a>K přiřazení do kategorií na element kódu

-   Otevřete soubor .dgml v textovém editoru nebo editoru XML.

-   Najít `<Node/>` element pro tento element kódu, který chcete.

-   V `<Node/>` elementu, přidejte `Category` atributu zadejte název kategorie. Příklad:

    ```xml
    <Nodes>
       <Node Id="MyNode" Category="MyCategory" />
    </Nodes>
    ```

     Přidat `<Category/>` elementu, který chcete `<Categories>` tak, aby můžete použít `Label` atribut zadat text k zobrazení této kategorie:

    ```xml
    <Categories>
       <Category Id="MyCategory" Label="My Category" />
    </Categories>
    ```

#### <a name="to-assign-a-category-to-a-link"></a>Přiřazení kategorie propojení

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Najít `<Link/>` elementu, který obsahuje názvy element kódu zdrojový a cílový element kódu.

3.  V `<Link/>` elementu, přidejte `Category` atributu zadejte název kategorie. Příklad:

    ```xml
    <Links>
       <Link Source="MyFirstNode" Target="MySecondNode" Category="MyCategory"
    </Links>
    ```

4.  Přidat `<Category/>` elementu, který chcete `<Categories>` tak, aby můžete použít `Label` atribut zadat text k zobrazení této kategorie:

    ```xml
    <Categories>
       <Category Id="MyCategory" Label="My Category" />
    </Categories>
    ```

#### <a name="to-create-hierarchical-categories"></a>Vytvoření hierarchických kategorií

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Přidat `<Category/>` element pro nadřazené kategorie a poté přidejte `BasedOn` atribut kategorie podřízeného `<Category/>` elementu.

     Příklad:

    ```xml
    <Nodes>
       <Node Id="MyFirstNode" Label="My First Node" Category= "MyCategory" />
       <Node Id="MySecondNode" Label="My Second Node" />
    </Nodes>
    <Links>
       <Link Source="MyFirstNode" Target="MySecondNode" />
    </Links>
    <Categories>
       <Category Id="MyCategory" Label="My Category" BasedOn="MyParentCategory"/>
       <Category Id="MyParentCategory" Label="My Parent Category" Background="Green"/>
    </Categories>
    ```

     V tomto příkladu pozadí `MyFirstNode` zelený protože jeho `Category` dědí atribut `Background` atribut `MyParentCategory`.

##  <a name="AddReferences"></a> Dokumenty nebo adresy URL propojit elementy kódu a odkazy
 Můžete propojit dokumenty nebo adresy URL elementy kódu nebo odkazy úprav souboru .dgml mapy a přidáním `Reference` atribut `<Node/>` element pro element kódu nebo `<Link/>` element pro připojení. Pak můžete otevřít a zobrazit tento obsah z element kódu nebo odkaz. `Reference` Atribut určuje cestu k obsahu. To může být cesta relativní k umístění souboru .dgml nebo absolutní cesta.

> [!CAUTION]
>  Pokud použijete relativní cestu a soubor .dgml bude přesunut do jiného umístění, pak tuto cestu nebude možné interpretovat. Při pokusu o otevření a zobrazení propojeného obsahu, dojde k chybě oznamující, že obsah nelze zobrazit.

 Například můžete chtít propojit následující elementy kódu:

-   Popis změny na třídu, můžete propojit adresu URL element kódu a pracovní, dokumentu nebo jiný soubor .dgml na tento element kódu pro třídu.

-   Diagram závislostí může propojit na skupiny kódu element, který představuje vrstvu v Logická architektura softwaru.

-   Pokud chcete zobrazit další informace o komponenty, která vystavuje rozhraní, můžete propojit diagram součásti na tento element kódu pro toto rozhraní.

-   Element kódu propojte pracovní položky sady Team Foundation Server nebo chyb nebo některé další informace, které se vztahuje k elementu kódu.

#### <a name="to-link-a-document-or-url-to-a-code-element"></a>Propojení dokumentu nebo adresa URL na element kódu

1.  Otevřete soubor .dgml v textovém editoru nebo editoru XML.

2.  Najít `<Node/>` element pro tento element kódu, který chcete.

3.  Proveďte jednu z úloh z následující tabulky:

     Element jednoho kódu

    -   V `<Node/>` nebo `<Link/>` elementu, přidejte `Reference` atribut k určení umístění elementu kódu.

        > [!NOTE]
        >  Může mít jen jeden `Reference` atribut na element.

     Příklad:

    ```xml
    <Nodes>
       <Node Id="MyNode" Reference="MyDocument.txt" />
    </Nodes>
    <Properties>
       <Property Id="Reference" Label="My Document" DataType="System.String" IsReference="True" />
    </Properties>
    ```

     Více elementy kódu

    1.  V `<Node/>` nebo `<Link/>` elementu, přidá nový atribut. k určení umístění každého odkazu.

    2.  V `<Properties>` části:

        1.  Přidat `<Property/>` element pro každý nový typ odkazu.

        2.  Nastavte `Id` atribut název atributu pro nový odkaz.

        3.  Přidat `IsReference` atribut a nastavte ji na `True` odkazovat na elementu kódu **přejít na referenční** místní nabídky.

        4.  Použití `Label` atribut určete zobrazovaný text na tento element kódu **přejít na referenční** místní nabídky.

     Příklad:

    ```xml
    <Nodes>
       <Node Id="MyNode" SequenceDiagram="MySequenceDiagram.sequencediagram" ActiveBugs="MyActiveBugs.wiq"/>
    </Nodes>
    <Properties>
       <Property Id="SequenceDiagram" Label="My Sequence Diagram" DataType="System.String" IsReference="True" />
       <Property Id="ActiveBugs" Label="Active Bugs" DataType="System.String" IsReference="True" />
    </Properties>
    ```

     Na mapě zobrazí se název elementu kódu podtržené. Když otevřete místní nabídku pro tento element kódu nebo odkaz, zobrazí se **přejděte na odkaz** místní nabídky, která obsahuje elementy propojené kódu můžete zvolit.

4.  Použití `ReferenceTemplate` atributu zadejte běžné řetězec, jako je například adresu URL, která používá několik odkazů místo opakující se tento řetězec v dokumentaci.

     `ReferenceTemplate` Atribut určuje zástupný symbol pro hodnotu odkazu. V následujícím příkladu `{0}` zástupný symbol v `ReferenceTemplate` atribut budou nahrazeny hodnoty `MyFirstReference` a `MySecondReference` atributy v `<Node/>` elementu, který chcete vytvořit úplnou cestu:

    ```xml
    <Nodes>
       <Node Id="MyNode" MyFirstReference="MyFirstDocument" MySecondReference="MySecondDocument"/>
       <Node Id="MySecondNode" MyFirstReference="AnotherFirstDocument" MySecondReference="AnotherSecondDocument"/>
    </Nodes>
    <Properties>
       <Property Id="MyFirstReference" Label="My First Document" DataType="System.String" IsReference="True" ReferenceTemplate="http://www.Fabrikam.com/FirstDocuments/{0}.asp"/>
       <Property Id="MySecondReference" Label="My Second Document" DataType="System.String" IsReference="True" ReferenceTemplate=" http://www.Fabrikam.com/SecondDocuments/{0}.asp"/>
    </Properties>
    ```

5.  K zobrazení element odkazovaného kódu nebo elementy kódu z mapování, otevřete místní nabídku pro tento element kódu nebo odkaz. Zvolte **přejít na referenční** a pak tento element kódu.

## <a name="see-also"></a>Viz také

- [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)
- [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)
- [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)
- [Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)
- [Referenční dokumentace jazyka přímého značení grafů (DGML)](../modeling/directed-graph-markup-language-dgml-reference.md)
