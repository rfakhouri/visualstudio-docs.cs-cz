---
title: Položka – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Item Element [MSBuild]
- <Item> Element [MSBuild]
ms.assetid: dcef5f91-0613-4bfc-8ee9-d7004bb6d3a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b55cadc738fb54b1a7fe07a2d891103c0daa755d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31576947"
---
# <a name="item-element-msbuild"></a>Item – prvek (MSBuild)
Obsahuje uživatelem definovanou položku a jeho metadata. Každá položka, která se používá v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu musí být zadány jako podřízená položka `ItemGroup` elementu.  

 \<Project>  
 \<ItemGroup >  
 \<Položka >  

## <a name="syntax"></a>Syntaxe  

```  
<Item Include="*.cs"  
        Exclude="MyFile.cs"  
        Remove="RemoveFile.cs"  
        Condition="'String A'=='String B'" >  
    <ItemMetadata1>...</ItemMetadata1>  
    <ItemMetadata2>...</ItemMetadata2>  
</Item>  
```  

## <a name="specify-metadata-as-attributes"></a>Zadejte metadat jako atributy
MSBuild 15.1 nebo novější veškerá metadata, s názvem, který není v konfliktu s aktuální seznam atributů může být volitelně vyjádřený jako atribut.

Například pokud chcete zadat seznam balíčků NuGet, běžně používáte něco jako následující syntaxi.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1-beta1<Version>
  </PackageReference>
</ItemGroup>
```

Teď však můžete předat `Version` metadat jako atribut, například v následující syntaxi:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1-beta1" />  
</ItemGroup>
```

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Include`|Nepovinný atribut.<br /><br /> Soubor nebo zástupný znak pro zahrnutí do seznamu položek.|  
|`Exclude`|Nepovinný atribut.<br /><br /> Soubor nebo zástupných znaků, které chcete vyloučit ze seznamu položek.|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  
|`Remove`|Nepovinný atribut.<br /><br /> Soubor nebo zástupný znak odebrat ze seznamu položek.<br /><br />|  
|`KeepDuplicates`|Nepovinný atribut.<br /><br /> Určuje, zda by měl být pokud je přesný duplikát stávající položku Přidat položku k cílové skupině. Pokud zdrojové a cílové položky stejné `Include` hodnotu, ale rozdílná metadata, položka je přidaný i když `KeepDuplicates` je nastaven na `false`. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).<br /><br /> Tento atribut je platný pouze v případě, že je zadán pro položku v `ItemGroup` který se v `Target`.|  
|`KeepMetadata`|Nepovinný atribut.<br /><br /> Metadata pro zdroj položky, které chcete přidat do cílové položky. Pouze metadata, jejichž názvy jsou určené v seznamu oddělený středníkem přenesou z položky zdroj cílová položka. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).<br /><br /> Tento atribut je platný pouze v případě, že je zadán pro položku v `ItemGroup` který se v `Target`.|  
|`RemoveMetadata`|Nepovinný atribut.<br /><br /> Metadata pro položky zdroje není přenášet do cílové položky. Všechna metadata se přenese z položky zdroje na cílová položka s výjimkou metadata jejichž názvy jsou obsaženy v seznamu názvů oddělených středníky. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).<br /><br /> Tento atribut je platný pouze v případě, že je zadán pro položku v `ItemGroup` který se v `Target`.|  
|`Update`|Nepovinný atribut. (K dispozici pouze pro .NET Core projektů Visual Studio 2017 nebo novější).<br /><br /> Umožňuje upravit metadata souboru, který je zahrnutý pomocí glob.<br /><br />  Tento atribut je platný pouze v případě, že je zadán pro položku v `ItemGroup` není součástí `Target`.|  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Itemmetadata –](../msbuild/itemmetadata-element-msbuild.md)|Klíč metadata uživatelem definovanou položku, který obsahuje hodnotu položky metadat. Může být nula nebo více `ItemMetadata` elementů v položku.|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Element seskupení položek.|  

## <a name="remarks"></a>Poznámky  
 `Item` elementy definovat vstupy do systému sestavení a jsou seskupené do kolekce položky, které jsou založené na jejich názvy uživatelem definované kolekci. Tyto položky kolekce se dají použít jako parametry pro [úlohy](../msbuild/msbuild-tasks.md), který pomůže jednotlivé položky v kolekci podle kroků procesu sestavení. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).  

 Pomocí zápisu `@(` *myType* `)` umožňuje kolekce položek typu *myType* být rozšířena do seznam řetězců oddělených středníky, a předaný parametr. Pokud je parametr typu `string`, je hodnota parametru seznamu elementů, oddělené středníky. Pokud je parametr pole řetězců (`string[]`), pak každý prvek budou vložena do pole na základě umístění středníky. Pokud je úloha parametr typu <xref:Microsoft.Build.Framework.ITaskItem> `[]`, hodnota bude obsah kolekce položek spolu s veškerá metadata, připojit. Pro každou položku vymezení pomocí znaků než středníkem, použijte syntaxi `@(` *myType*`, '`*oddělovače*`')`.  

 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Modul vyhodnocení zástupné znaky, jako `*` a `?` a rekurzivní zástupné znaky, jako `/**/*.cs`. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).  

## <a name="examples"></a>Příklady  
 Následující příklad kódu ukazuje, jak deklarovat dvě položky typu `CSFile`. Druhý deklarovaný položka obsahuje metadata, která má `MyMetadata` nastavena na `HelloWorld`.  

```xml  
<ItemGroup>  
    <CSFile Include="engine.cs; form.cs" />  
    <CSFile Include="main.cs" >  
        <MyMetadata>HelloWorld</MyMetadata>  
    </CSFile>  
</ItemGroup>  
```  
Následující příklad kódu ukazuje, jak používat `Update` atribut upravit metadata v souboru s názvem somefile.cs, který byl zahrnut prostřednictvím glob. (K dispozici pouze pro .NET Core projektů Visual Studio 2017 nebo novější).

```xml  
<ItemGroup>
    <Compile Update="somefile.cs">  // or Update="*.designer.cs"
        <MetadataKey>MetadataValue</MetadataKey>
    </Compile>
</ItemGroup>  
```  


## <a name="see-also"></a>Viz také  
 [Položky](../msbuild/msbuild-items.md)   
 [Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
