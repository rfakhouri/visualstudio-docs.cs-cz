---
title: "Řízené reference jazyka značení grafů (DGML) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc3e4ae7-60fa-4e22-9227-98020b480b73
caps.latest.revision: "8"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: e1ea2e37668806849b88d1fb7d6a15142518c076
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="directed-graph-markup-language-dgml-reference"></a>Referenční dokumentace jazyka přímého značení grafů (DGML)
Přímé, že jazyk značení grafů (DGML) popisuje informace, které slouží pro vizualizaci a provádět analýzu složitost a je formát použitý k zachování map kódu v sadě Visual Studio. K popisu cyklické i Acyklické grafy směrovanou používá jednoduchý XML. Orientovaný graf je sada uzlů, které jsou propojeny pomocí propojení neboli hran. Uzly a propojení mohou být použity pro reprezentaci síťových struktur, jako jsou například prvky v softwarovém projektu.  
  
 Všimněte si, že některé verze sady Visual Studio podporují pouze podmnožinu DGML možnosti najdete v části [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
> [!NOTE]
>  Při úpravách souboru .dgml usnadňuje technologie IntelliSense určení atributů, které jsou k dispozici pro každý prvek, a jejich hodnot. Pro určení barvy v atributu použijte názvy pro běžné barvy, například „Blue“ (modrá) nebo šestnáctkové hodnoty ARGB, jako je například „#ffa0b1c3“. Jazyk DGML používá malou podmnožinu formátů definice barev Windows Presentation Foundation (WPF). Další informace najdete v tématu [barvy třída](http://go.microsoft.com/fwlink/?LinkId=182345).  
  
##  <a name="DGML"></a>Syntaxe DGML  
 Následující tabulka popisuje typy elementů, které se používají v DGML:  
  
-   `<DirectedGraph></DirectedGraph>`  
  
     Tento element má kořenový element dokumentu mapy (.dgml) kódu. V rámci tohoto prvku jsou všechny ostatní prvky jazyka DGML.  
  
     Následující seznam popisuje volitelné atributy, které lze vložit:  
  
     `Background`-Barva pozadí map  
  
     `BackgroundImage`-Umístění soubor obrázku, který chcete použít jako pozadí map.  
  
     `GraphDirection`– Když je nastavená mapy na strom rozložení (`Sugiyama`), uspořádání uzlů tak, aby Většina odkazů toku v zadaném směru: `TopToBottom`, `BottomToTop`, `LeftToRight`, nebo `RightToLeft`. V tématu [Změna rozložení mapy](../modeling/browse-and-rearrange-code-maps.md#Selecting).  
  
     `Layout`– Nastavte mapy na následující rozložení: `None`, `Sugiyama` (stromu rozložení), `ForceDirected` (rychlé clustery), nebo `DependencyMatrix`. V tématu [Změna rozložení mapy](../modeling/browse-and-rearrange-code-maps.md#Selecting).  
  
     `NeighborhoodDistance`-Pokud mapy je nastaven na rozložení stromu nebo rozložení rychlé clustery, zobrazit pouze uzly, které jsou zadané číslo (1-7) odkazů mimo vybrané uzly. V tématu [Změna rozložení mapy](../modeling/browse-and-rearrange-code-maps.md#Selecting).  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" Background="Blue" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Nodes>  
          ...  
       </Nodes>  
       <Links>  
          ...  
       </Links>  
       <Categories>  
          ...  
       </Categories>  
       <Properties>  
          ...  
       </Properties>  
    </DirectedGraph>  
    ```  
  
-   `<Nodes></Nodes>`  
  
     Tento volitelný element obsahuje seznam `<Node/>` elementy, které definují uzly na mapě. Další informace najdete v tématu `<Node/>` elementu.  
  
    > [!NOTE]
    >  Když odkazujete nedefinované uzlu v `<Link/>` elementu mapy vytvoří `<Node/>` element automaticky.  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Nodes>  
          <Node ... />  
       </Nodes>  
       <Links>  
          <Link ... />  
       </Links>  
    </DirectedGraph>  
    ```  
  
-   `<Node/>`  
  
     Tento prvek definuje jeden uzel. Zobrazí se v rámci `<Nodes><Nodes/>` element seznamu.  
  
     Tento prvek musí obsahovat následující atributy:  
  
     `Id`-Jedinečný název uzlu a výchozí hodnota `Label` atribut, pokud žádné samostatné `Label` zadán atribut. Tento název se musí shodovat `Source` nebo `Target` atribut odkaz, který odkazuje.  
  
     Následující seznam popisuje některé volitelné atributy, které lze vložit:  
  
     `Label`-Zobrazovaný název uzlu.  
  
     Atributy stylu. V tématu [mapuje přizpůsobit kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
     `Category`-Název kategorie, která identifikuje elementy, které sdílejí tento atribut. Další informace najdete v tématu `<Category/>` elementu.  
  
     `Property`-Název vlastnosti, která identifikuje prvky, které mají stejnou hodnotu vlastnosti. Další informace najdete v tématu `<Property/>` elementu.  
  
     `Group`– Pokud uzel obsahuje jiné uzly, nastavte tento atribut na `Expanded` nebo `Collapsed` zobrazit nebo skrýt její obsah. Musí existovat `<Link/>` element, který obsahuje `Category="Contains"` atribut a Určuje nadřazený uzel jako zdrojový uzel a podřízený uzel jako cílový uzel. V tématu [skupiny elementy kódu](../modeling/customize-code-maps-by-editing-the-dgml-files.md#OrganizeNodes).  
  
     `Visibility`– Nastavte tento atribut na `Visible`, `Hidden`, nebo `Collapsed`. Používá `System.Windows.Visibility`. V tématu [skrytí nebo zobrazení uzlů a odkazy](../modeling/browse-and-rearrange-code-maps.md#HidingShowing).  
  
     `Reference`– Nastavte tento atribut propojení dokumentu nebo adresa URL. V tématu [dokumenty nebo adresy URL propojit elementy kódu a odkazy](../modeling/customize-code-maps-by-editing-the-dgml-files.md#AddReferences).  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Nodes>  
          <Node Id="Driver" Label="Student" Category="Person" />  
          <Node Id="Passenger" Label="Instructor" Category="Person" />  
          <Node Id="Car" Label="Car" Category="Automobile" />  
          <Node Id="Truck" Label="Truck" Category="Automobile" />  
       </Nodes>  
       <Links>  
          <Link ... />  
       </Links>  
       <Categories>  
          <Category Id="Person" Background="Orange" />  
          <Category Id="Automobile" Background="Yellow"/>  
       </Categories>  
    </DirectedGraph>  
    ```  
  
-   `<Links></Links>`  
  
     Tento prvek obsahuje seznam `<Link>` elementy, které definují propojení mezi uzly. Další informace najdete v tématu `<Link/>` elementu.  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Links>  
          <Link ... />  
       </Links>  
    </DirectedGraph>  
    ```  
  
-   `<Link/>`  
  
     Tento prvek definuje jedno propojení, které připojuje zdrojový uzel k cílovému uzlu. Zobrazí se v rámci `<Links></Links>` element seznamu.  
  
    > [!NOTE]
    >  Pokud tento element odkazuje nedefinované uzlu, mapy dokumentu automaticky vytvoří uzel, který má zadané atributy, pokud existuje.  
  
     Tento prvek musí obsahovat následující atributy:  
  
     `Source`-Zdrojový uzel odkazu  
  
     `Target`-Cílový uzel odkazu  
  
     Následující seznam popisuje některé volitelné atributy, které lze vložit:  
  
     `Label`-Zobrazovaný název odkazu  
  
     Atributy stylu. V tématu [mapuje přizpůsobit kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
     `Category`-Název kategorie, která identifikuje elementy, které sdílejí tento atribut. Další informace najdete v tématu `<Category/>` elementu.  
  
     `Property`-Název vlastnosti, která identifikuje prvky, které mají stejnou hodnotu vlastnosti. Další informace najdete v tématu `<Property/>` elementu.  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Nodes>  
          <Node Id="Driver" Label="Student" Category="Person" />  
          <Node Id="Passenger" Label="Instructor" Category="Person" />  
          <Node Id="Car" Label="Car" Category="Automobile" />  
          <Node Id="Truck" Label="Truck" Category="Automobile" />  
       </Nodes>  
       <Links>  
          <Category Id="Person" Background="Orange" />  
          <Category Id="Automobile" Background="Yellow"/>  
          <Link Source="Driver" Target="Car" Label="Passed" Stroke="Black" Background="Green" Category="PassedTest" />  
          <Link Source="Driver" Target="Truck" Label="Failed" Stroke="Black" Background="Red" Category="PassedTest" />  
       </Links>  
    </DirectedGraph>  
    ```  
  
-   `<Categories></Categories>`  
  
     Tento prvek obsahuje seznam `<Category/>` elementy. Další informace najdete v tématu `<Category/>` elementu.  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Categories>  
           <Category ... />  
       </Categories>  
    </DirectedGraph>  
    ```  
  
-   `<Category/>`  
  
     Tento element definuje `Category` atribut, který se používá k identifikaci elementy, které sdílejí tento atribut. A `Category` atribut slouží k uspořádání elementů mapy, zadejte pro sdílené atributy prostřednictvím dědičnosti nebo definovat další metadata.  
  
     Tento prvek musí obsahovat následující atributy:  
  
     `Id`-Jedinečný název kategorie a výchozí hodnota `Label` atribut, pokud žádné samostatné `Label` zadán atribut.  
  
     Následující seznam popisuje některé volitelné atributy, které lze vložit:  
  
     `Label`-A čtečky popisný název pro kategorii.  
  
     `BasedOn`-Nadřazené kategorie, ze kterého `<Category/>` aktuálního elementu dědí.  
  
     V příkladu pro tento element `FailedTest` kategorie dědí jeho `Stroke` atribut z `PassedTest` kategorie. Najdete v části "postup vytvoření hierarchické kategorie" v [mapuje přizpůsobit kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
     Kategorie také poskytují některé základní šablony chování, které řídí vzhled uzly a odkazy, jakmile se zobrazí na mapě. V tématu [mapuje přizpůsobit kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Nodes>  
          <Node Id="Driver" Label="Driver" Category="Person" />  
          <Node Id="Car" Label="Car" Category="Automobile" />  
          <Node Id="Truck" Label="Truck" Category="Automobile" />  
          <Node Id="Passenger" Category="Person" />  
       </Nodes>  
       <Links>  
          <Link Source="Driver" Target="Car" Label="Passed" Category="PassedTest" />  
          <Link Source="Driver" Target="Truck" Label="Failed" Category="FailedTest" />  
       </Links>  
       <Categories>  
          <Category Id="Person" Background="Orange" />  
          <Category Id="Automobile" Background="Yellow"/>  
          <Category Id="PassedTest" Label="Passed" Stroke="Black" Background="Green" />  
          <Category Id="FailedTest" Label="Failed" BasedOn="PassedTest" Background="Red" />  
       </Categories>  
    </DirectedGraph>  
    ```  
  
-   `<Properties></Properties>`  
  
     Tento prvek obsahuje seznam `<Property/>` elementy. Další informace najdete v tématu `<Property/>` elementu.  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Properties>  
           <Property ... />  
       </Properties>  
    </DirectedGraph>  
    ```  
  
-   `<Property/>`  
  
     Tento element definuje `Property` atribut, který můžete použít k přiřazení hodnoty k žádnému DGML element nebo atribut, včetně kategorie a dalších vlastností.  
  
     Tento prvek musí obsahovat následující atributy:  
  
    -   `Id`-Jedinečný název vlastnosti a výchozí hodnota `Label` atribut, pokud žádné samostatné `Label` zadán atribut.  
  
    -   `DataType`-Typ dat uložených vlastností  
  
     Pokud chcete, aby vlastnost zobrazí v **vlastnosti** okna, použijte `Label` vlastnosti k určení, zobrazovaný název vlastnosti.  
  
     V tématu [kategorie přiřadit elementy kódu a odkazy](../modeling/customize-code-maps-by-editing-the-dgml-files.md#AssignCategories).  
  
     Příklad:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
       <Nodes>  
          <Node Id="Driver" Label="Driver" Category="Person" DrivingAge="18"/>  
          <Node Id="Car" Label="Car" Category="Automobile" />  
          <Node Id="Truck" Label="Truck" Category="Automobile" />  
          <Node Id="Passenger" Category="Person" />  
       </Nodes>  
       <Links>  
          <Link Source="Driver" Target="Car" Label="Passed" Category="PassedTest" />  
          <Link Source="Driver" Target="Truck" Label="Failed" Category="FailedTest" />  
       </Links>  
       <Categories>  
          <Category Id="Person" Background="Orange" />  
          <Category Id="Automobile" Background="Yellow"/>  
          <Category Id="PassedTest" Label="Passed" Stroke="Black" Background="Green" />  
          <Category Id="FailedTest" Label="Failed" BasedOn="PassedTest" Background="Red" />  
       </Categories>  
       <Properties>  
           <Property Id="DrivingAge" Label="Driving Age" DataType="System.Int32" />  
       </Properties>  
    </DirectedGraph>  
    ```  
  
###  <a name="AddAlias"></a>Aliasy pro běžně používané cesty  
 Nahrazení běžně používaných cest aliasy pomáhá zmenšit velikost souboru .dgml a snižuje čas potřebný k načtení nebo uložení souboru. Chcete-li vytvořit alias, přidejte `<Paths></Paths>` na konci souboru .dgml. V této části, přidejte `<Path/>` elementu, který chcete definovat alias pro cestu:  
  
```xml  
<Paths>  
   <Path Id="MyPathAlias" Value="C:\...\..." />  
</Paths>  
```  
  
 Chcete-li alias z element v souboru .dgml, uzavřete `Id` z \<cesta / > element s znak dolaru ($) a závorky (()):  
  
```xml  
<Nodes>  
   <Node Id="MyNode" Reference="$(MyPathAlias)MyDocument.txt" />  
</Nodes>  
<Properties>  
   <Property Id="Reference" Label="My Document" DataType="System.String" IsReference="True" />  
</Properties>  
```  
  
## <a name="see-also"></a>Viz také  
 [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)   
 [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)