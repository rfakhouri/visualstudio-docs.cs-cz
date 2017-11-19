---
title: "Položky nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MSBuild, Items
ms.assetid: d762eff4-c92a-4b5f-a944-1ca30aa22319
caps.latest.revision: "35"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a306f7cda287e41efc0cb59cf5a75c7111d32c39
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-items"></a>Položky nástroje MSBuild
Položky nástroje MSBuild jsou vstupy do systému sestavení a obvykle představují soubory. Položky jsou seskupeny do typů položek, které jsou založené na jejich názvy elementů. Typy položek jsou pojmenované seznam položek, které lze použít jako parametry pro úlohy. Úlohy pomocí hodnot položky podle kroků procesu sestavení.  
  
 Protože položky jsou pojmenované podle typu položky, do které patří, podmínky "položka" a "hodnota položky" zaměnitelné.  
  
 **V tomto tématu**  
  
-   [Vytváření položek v souboru projektu](#BKMK_Creating1)  
  
-   [Vytváření položek během provádění](#BKMK_Creating2)  
  
-   [Odkazování na položky v souboru projektu](#BKMK_ReferencingItems)  
  
-   [Použití zástupných znaků k určení položek](#BKMK_Wildcards)  
  
-   [Používání atributu vyloučení](#BKMK_ExcludeAttribute)  
  
-   [Metadata položky](#BKMK_ItemMetadata)  
  
    -   [Odkazování na Metadata položek v souboru projektu](#BKMK_ReferencingItemMetadata)  
  
    -   [Metadata známé položky](#BKMK_WellKnownItemMetadata)  
  
    -   [Převod typů položek na základě metadat](#BKMK_Transforming)  
  
-   [Definice položek](#BKMK_ItemDefinitions)  
  
-   [Atributy pro položky ItemGroup cíl](#BKMK_AttributesWithinTargets)  
  
    -   [Odeberte atribut](#BKMK_RemoveAttribute)  
  
    -   [Atribut KeepMetadata](#BKMK_KeepMetadata)  
  
    -   [Atribut RemoveMetadata](#BKMK_RemoveMetadata)  
  
    -   [Atribut KeepDuplicates](#BKMK_KeepDuplicates)  
  
##  <a name="BKMK_Creating1"></a>Vytváření položek v souboru projektu  
 Deklarování položky v souboru projektu jako podřízené prvky [ItemGroup](../msbuild/itemgroup-element-msbuild.md) element. Název podřízený element je typu položky. `Include` Položky (soubory), které budou součástí této typ položky Určuje atribut elementu. Například následující kód XML vytvoří typ položky, který je pojmenován `Compile`, což zahrnuje dva soubory.  
  
```xml  
<ItemGroup>  
    <Compile Include = "file1.cs"/>  
    <Compile Include = "file2.cs"/>  
</ItemGroup>  
```  
  
 Položka "file2.cs" není nahradit položku "file1.cs"; Místo toho se připojí název souboru do seznamu hodnot pro `Compile` typ položky. Položku nelze odebrat z typ položky během zkušební fáze sestavení.  
  
 Následující kód XML ve výchozím nastavení vytvoří stejný typ položky deklarace oba soubory v jednom `Include` atribut. Všimněte si, že názvy souborů jsou odděleny středníkem.  
  
```xml  
<ItemGroup>  
    <Compile Include = "file1.cs;file2.cs"/>  
</ItemGroup>  
```  
  
##  <a name="BKMK_Creating2"></a>Vytváření položek během provádění  
 Položky, které jsou mimo [cíl](../msbuild/target-element-msbuild.md) elementy přiřazené hodnoty během zkušební fáze sestavení. Během fáze následné provádění může se položky vytvoří nebo upraví následujícími způsoby:  
  
-   Všechny úlohy můžete emitování položku. Pro vydávání položku, [úloh](../msbuild/task-element-msbuild.md) elementu musí být podřízenou [výstup](../msbuild/output-element-msbuild.md) element, který má `ItemName` atribut.  
  
-   [Createitem –](../msbuild/createitem-task.md) úloh můžete emitování položku. Tento způsob využití je zastaralý.  
  
-   Od verze rozhraní .NET Framework 3.5, `Target` může obsahovat elementy [ItemGroup](../msbuild/itemgroup-element-msbuild.md) prvky, které mohou obsahovat položku elementy.  
  
##  <a name="BKMK_ReferencingItems"></a>Odkazování na položky v souboru projektu  
 Chcete-li typů položek v souboru projektu, použijte syntaxi @(`ItemType`). Například by reference typu položky v předchozím příkladu pomocí `@(Compile)`. Pomocí této syntaxe je předat položky do úlohy zadáním typ položky jako parametr funkce této úlohy. Další informace najdete v tématu [postup: Vyberte soubory k sestavení](../msbuild/how-to-select-the-files-to-build.md).  
  
 Ve výchozím nastavení jsou položky Typ položky oddělené středníkem (;), pokud není rozbalen. Můžete použít syntaxi @(*ItemType*, se*oddělovače*') k určení oddělovač jiné než výchozí. Další informace najdete v tématu [postupy: zobrazení k položce seznamu oddělených čárkami](../msbuild/how-to-display-an-item-list-separated-with-commas.md).  
  
##  <a name="BKMK_Wildcards"></a>Použití zástupných znaků k určení položek  
 Můžete použít **, \*, a? zástupné znaky jako vstupy pro sestavení místo výpis každý soubor samostatně zadat skupiny souborů.  
  
-   Na? zástupný znak odpovídá jeden znak.  
  
-   * Zástupný znak odpovídá žádnému nebo více znakům.  
  
-   ** Zástupný znak pořadí odpovídá částečné cesty.  
  
 Například můžete zadat všechny .cs soubory v adresáři, který obsahuje soubor projektu pomocí následující element v souboru projektu.  
  
```xml  
<CSFile Include="*.cs"/>  
```  
  
 Následující element vybere všechny soubory vb na jednotce D::  
  
```xml  
<VBFile Include="D:/**/*.vb"/>  
```  
  
 Další informace o zástupné znaky, najdete v části [postup: Vyberte soubory k sestavení](../msbuild/how-to-select-the-files-to-build.md).  
  
##  <a name="BKMK_ExcludeAttribute"></a>Používání atributu vyloučení  
 Může obsahovat elementy položky `Exclude` atribut, který vyloučí určité položky (soubory) z tohoto typu položky. `Exclude` Atribut se obvykle používá spolu s zástupné znaky. Například následující kód XML přidá každý .cs soubor v adresáři typu položky CSFile, s výjimkou `DoNotBuild.cs` souboru.  
  
```xml  
<ItemGroup>  
    <CSFile  Include="*.cs"  Exclude="DoNotBuild.cs"/>  
</ItemGroup>  
```  
  
 `Exclude` Atribut ovlivňuje pouze položky, které jsou přidávány `Include` atribut v elementu položku, která obsahuje oba. V následujícím příkladu by vyloučení souboru Form1.cs, která byla přidána v předchozí položce elementu.  
  
```xml  
<Compile Include="*.cs" />  
<Compile Include="*.res" Exclude="Form1.cs">  
```  
  
 Další informace najdete v tématu [postupy: vyloučení souborů ze sestavení](../msbuild/how-to-exclude-files-from-the-build.md).  
  
##  <a name="BKMK_ItemMetadata"></a>Metadata položky  
 Položky mohou obsahovat metadata kromě informací v `Include` a `Exclude` atributy. Tato metadata lze úlohy, které vyžadují další informace o položkách nebo úkoly služby batch a cíle. Další informace najdete v tématu [Batching](../msbuild/msbuild-batching.md).  
  
 Metadata jsou kolekce páry klíč hodnota, které jsou deklarované v souboru projektu jako podřízené prvky elementu položky. Název elementu podřízené je název metadat a podřízený element hodnotu hodnota metadat.  
  
 Metadata se přidružené položky elementu, který jej obsahuje. Například následující kód XML přidá `Culture` metadata, která má hodnotu `Fr` "one.cs" a "two.cs" položky CSFile typ položky.  
  
```xml  
<ItemGroup>  
    <CSFile Include="one.cs;two.cs">  
        <Culture>Fr</Culture>  
    </CSFile>  
</ItemGroup>  
```  
  
 Položka může mít nula nebo více hodnot metadat. Kdykoli můžete změnit hodnoty metadat. Pokud jste nastavili metadata na prázdnou hodnotu, je efektivně jej odebrat z buildu.  
  
###  <a name="BKMK_ReferencingItemMetadata"></a>Odkazování na Metadata položek v souboru projektu  
 Metadata položek v souboru projektu, můžete odkazovat pomocí syntaxe %(`ItemMetadataName`). Pokud existuje nejednoznačnosti, máte nárok odkaz pomocí názvu typu položky. For example, můžete zadat %(*ItemType.ItemMetaDataName*). Následující příklad používá zobrazení metadat pro dávkové úlohy zpráv. Další informace o tom, jak používat metadata položky pro dávkování najdete v tématu [Metadata položek v dávkování úloh](../msbuild/item-metadata-in-task-batching.md).  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Stuff Include="One.cs" >  
            <Display>false</Display>  
        </Stuff>  
        <Stuff Include="Two.cs">  
            <Display>true</Display>  
        </Stuff>  
    </ItemGroup>  
    <Target Name="Batching">  
        <Message Text="@(Stuff)" Condition=" '%(Display)' == 'true' "/>  
    </Target>  
</Project>  
```  
  
###  <a name="BKMK_WellKnownItemMetadata"></a>Metadata známé položky  
 Pokud je přidat položku do typ položky, že položka přiřazené některé známé metadat. Například všechny položky mají dobře známé metadata `%(Filename)`, jehož hodnota je název souboru položky. Další informace najdete v tématu [Metadata známé položky](../msbuild/msbuild-well-known-item-metadata.md).  
  
###  <a name="BKMK_Transforming"></a>Převod typů položek na základě metadat  
 Položky seznamů lze do nové položky seznamů transformovat na základě metadat. Například můžete převést typ položky `CppFiles` s položky, které představují sada soubory do seznam soubory .obj odpovídající pomocí výrazu `@(CppFiles -> '%(Filename).obj')`.  
  
 Následující kód vytvoří `CultureResource` typ, který obsahuje kopie všech položky `EmbeddedResource` položky `Culture` metadat. `Culture` Hodnota metadat se změní na hodnotu novými metadaty `CultureResource.TargetDirectory`.  
  
```xml  
<Target Name="ProcessCultureResources">  
    <ItemGroup>  
        <CultureResource Include="@(EmbeddedResource)"  
            Condition="'%(EmbeddedResource.Culture)' != ''">  
            <TargetDirectory>%(EmbeddedResource.Culture) </TargetDirectory>  
        </CultureResource>  
    </ItemGroup>  
</Target>  
```  
  
 Další informace najdete v tématu [transformuje](../msbuild/msbuild-transforms.md).  
  
##  <a name="BKMK_ItemDefinitions"></a>Definice položek  
 Od verze rozhraní .NET Framework 3.5, můžete přidat výchozí metadata k libovolnému typu položky pomocí [ItemDefinitionGroup – element](../msbuild/itemdefinitiongroup-element-msbuild.md). Jako dobře známé metadata metadata výchozí souvisí s všechny položky typu položky, které zadáte. Explicitně můžete přepsat výchozí metadata v definici položky. Například následující kód XML dává `Compile` položky "one.cs" a "three.cs" metadata `BuildDay` s hodnotou "Pondělí". Kód poskytuje položku "two.cs" metadata `BuildDay` s hodnotou "Úterý".  
  
```xml  
<ItemDefinitionGroup>  
    <Compile>  
        <BuildDay>Monday</BuildDay>  
    </Compile>  
</ItemDefinitionGroup>  
<ItemGroup>  
    <Compile Include="one.cs;three.cs" />  
    <Compile Include="two.cs">  
        <BuildDay>Tuesday</BuildDay>  
    </Compile>  
</ItemGroup>  
```  
  
 Další informace najdete v tématu [definice položek](../msbuild/item-definitions.md).  
  
##  <a name="BKMK_AttributesWithinTargets"></a>Atributy pro položky ItemGroup cíl  
 Od verze rozhraní .NET Framework 3.5, `Target` může obsahovat elementy [ItemGroup](../msbuild/itemgroup-element-msbuild.md) prvky, které mohou obsahovat položku elementy. Atributy v této části jsou platné, pokud jsou zadané pro položku v `ItemGroup` který se v `Target`.  
  
###  <a name="BKMK_RemoveAttribute"></a>Odeberte atribut  
 Položky v `ItemGroup` cíle může obsahovat `Remove` atribut, který odebere typ položky konkrétní položky (soubory). Tento atribut byla zavedena v rozhraní .NET Framework 3.5.  
  
 Následující příklad odebere všechny soubory .config typ položky kompilace.  
  
```xml  
<Target>  
    <ItemGroup>  
        <Compile Remove="*.config"/>  
    </ItemGroup>  
</Target>  
```  
  
###  <a name="BKMK_KeepMetadata"></a>Atribut KeepMetadata  
 Pokud v rámci cíl je generována položky, položka element může obsahovat `KeepMetadata` atribut. Pokud tento atribut je určen, se převede pouze metadata, která je uveden v seznamu názvů oddělených středníky z položky zdroje na cílová položka. Prázdnou hodnotu pro tento atribut je ekvivalentní není ho. `KeepMetadata` Atribut byla zavedena v rozhraní .NET Framework 4.5.  
  
 Následující příklad ukazuje, jak používat `KeepMetadata` atribut.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
ToolsVersion="4.0">  
  
    <ItemGroup>  
        <FirstItem Include="rhinoceros">  
            <Class>mammal</Class>  
            <Size>large</Size>  
        </FirstItem>  
  
    </ItemGroup>  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <SecondItem Include="@(FirstItem)" KeepMetadata="Class" />  
        </ItemGroup>  
  
        <Message Text="FirstItem: %(FirstItem.Identity)" />  
        <Message Text="  Class: %(FirstItem.Class)" />  
        <Message Text="  Size:  %(FirstItem.Size)"  />  
  
        <Message Text="SecondItem: %(SecondItem.Identity)" />  
        <Message Text="  Class: %(SecondItem.Class)" />  
        <Message Text="  Size:  %(SecondItem.Size)"  />  
    </Target>  
</Project>  
  
<!--  
Output:  
  FirstItem: rhinoceros  
    Class: mammal  
    Size:  large  
  SecondItem: rhinoceros  
    Class: mammal  
    Size:   
-->  
```  
  
###  <a name="BKMK_RemoveMetadata"></a>Atribut RemoveMetadata  
 Pokud v rámci cíl je generována položky, položka element může obsahovat `RemoveMetadata` atribut. Pokud tento atribut je určen, všechna metadata je přenést z položky zdroje na cílová položka s výjimkou metadata jejichž názvy jsou obsaženy v seznamu názvů oddělených středníky. Prázdnou hodnotu pro tento atribut je ekvivalentní není ho. `RemoveMetadata` Atribut byla zavedena v rozhraní .NET Framework 4.5.  
  
 Následující příklad ukazuje, jak používat `RemoveMetadata` atribut.  
  
```xml  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <MetadataToRemove>Size;Material</MetadataToRemove>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <Item1 Include="stapler">  
            <Size>medium</Size>  
            <Color>black</Color>  
            <Material>plastic</Material>  
        </Item1>  
    </ItemGroup>  
  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <Item2 Include="@(Item1)" RemoveMetadata="$(MetadataToRemove)" />  
        </ItemGroup>  
  
        <Message Text="Item1: %(Item1.Identity)" />  
        <Message Text="  Size:     %(Item1.Size)" />  
        <Message Text="  Color:    %(Item1.Color)" />  
        <Message Text="  Material: %(Item1.Material)" />  
        <Message Text="Item2: %(Item2.Identity)" />  
        <Message Text="  Size:     %(Item2.Size)" />  
        <Message Text="  Color:    %(Item2.Color)" />  
        <Message Text="  Material: %(Item2.Material)" />  
    </Target>  
</Project>  
  
<!--  
Output:   
  Item1: stapler  
    Size:     medium  
    Color:    black  
    Material: plastic  
  Item2: stapler  
    Size:       
    Color:    black  
    Material:   
-->  
```  
  
###  <a name="BKMK_KeepDuplicates"></a>Atribut KeepDuplicates  
 Pokud v rámci cíl je generována položky, položka element může obsahovat `KeepDuplicates` atribut. `KeepDuplicates`je `Boolean` atribut, který určuje, zda by měl být pokud je položka přesným duplikátem stávající položku Přidat položku k cílové skupině.  
  
 Pokud zdrojové a cílové položky mají stejnou hodnotu zahrnout ale rozdílná metadata, položka je přidána i v případě `KeepDuplicates` je nastaven na `false`. Prázdnou hodnotu pro tento atribut je ekvivalentní není ho. `KeepDuplicates` Atribut byla zavedena v rozhraní .NET Framework 4.5.  
  
 Následující příklad ukazuje, jak používat `KeepDuplicates` atribut.  
  
```xml  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Item1 Include="hourglass;boomerang" />  
        <Item2 Include="hourglass;boomerang" />  
    </ItemGroup>  
  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <Item1 Include="hourglass" KeepDuplicates="false" />  
            <Item2 Include="hourglass" />  
        </ItemGroup>  
  
        <Message Text="Item1: @(Item1)" />  
        <Message Text="  %(Item1.Identity)  Count: @(Item1->Count())" />  
        <Message Text="Item2: @(Item2)" />  
        <Message Text="  %(Item2.Identity)  Count: @(Item2->Count())" />  
    </Target>  
</Project>  
  
<!--  
Output:   
  Item1: hourglass;boomerang  
    hourglass  Count: 1  
    boomerang  Count: 1  
  Item2: hourglass;boomerang;hourglass  
    hourglass  Count: 2  
    boomerang  Count: 1  
-->  
```  
  
## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)  
 [Nástroje MSBuild](../msbuild/msbuild.md)   
 [Postupy: Vyberte soubory k sestavení](../msbuild/how-to-select-the-files-to-build.md)   
 [Postupy: vyloučení souborů ze sestavení](../msbuild/how-to-exclude-files-from-the-build.md)   
 [Postupy: zobrazení seznamu položek oddělených čárkami](../msbuild/how-to-display-an-item-list-separated-with-commas.md)   
 [Definice položek](../msbuild/item-definitions.md)   
 [Dávkování](../msbuild/msbuild-batching.md)   
 [Item – Element (MSBuild)](../msbuild/item-element-msbuild.md)