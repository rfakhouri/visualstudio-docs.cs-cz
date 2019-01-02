---
title: Dávkování nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
ms.assetid: d35c085b-27b8-49d7-b6f8-8f2f3a0eec38
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6b5f5f2a4d45500e9d96926d856f4895a1a144dc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53888000"
---
# <a name="msbuild-batching"></a>Dávkování nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] má schopnost rozdělení seznamů položek do různých kategorií nebo dávek, na základě položky metadat a spustit cíl nebo úloha jednou s jednotlivých dávek.  
  
## <a name="task-batching"></a>Dávkování úloh  
 Dávkování úloh můžete zjednodušit tím, že poskytuje způsob, jak rozdělení seznamů položek na jiné listy a každá z těchto dávky samostatně předat do úlohy soubory projektu. To znamená, že soubor projektu pouze musí mít úkolu a její atributy deklarované jednou, i když můžete spustit několikrát.  
  
 Určete, jestli má [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] provádět dávkové zpracování s úlohami pomocí %(\<ItemMetaDataName >) zápis v jednom z atributů úlohy. V následujícím příkladu se rozdělí `Example` na základě seznamu položek do dávek `Color` hodnotu položky metadat a předá do dávek `MyTask` úloh samostatně.  
  
> [!NOTE]
>  Pokud Neodkazovat seznam položek jinde v atributech úloh nebo může být nejednoznačný název metadat, můžete použít %(\<ItemCollection.ItemMetaDataName >) zápis k plnému určení hodnotu položky metadat pro dávkové zpracování.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Dávkování konkrétnější příklady najdete v tématu [metadata položek v dávkování úloh](../msbuild/item-metadata-in-task-batching.md).  
  
## <a name="target-batching"></a>Dávkování cíle  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kontroluje, pokud vstupy a výstupy cíle jsou aktuální předtím, než spustí cíl. Pokud se vstupy a výstupy jsou aktuální, je cíl vynechán. Pokud úkol uvnitř cíl využívá, dávkové zpracování, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] potřebuje k určení, zda je aktuální vstupy a výstupy pro jednotlivé skupiny položek. V opačném případě je cíl proveden pokaždé, když je spuštění.  
  
 Následující příklad ukazuje `Target` element, který obsahuje `Outputs` atributem %(\<ItemMetaDataName >) notaci. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Rozdělí `Example` na základě seznamu položek do dávek `Color` položky metadat a analyzovat časová razítka výstupních souborů pro jednotlivé dávky. Pokud výstupy z dávky nejsou aktuální, je spustit cíl. V opačném případě je cíl vynechán.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask"  
        Inputs="@(Example)"  
        Outputs="%(Color)\MyFile.txt">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Další příklad dávkování cíle, naleznete v tématu [metadata položek v dávkování cíle](../msbuild/item-metadata-in-target-batching.md).  
  
## <a name="property-functions-using-metadata"></a>Funkce vlastností pomocí metadat  
 Dávkování lze ovládat funkce vlastností, které zahrnují metadata. Například  
  
 `$([System.IO.Path]::Combine($(RootPath),%(Compile.Identity)))`  
  
 používá <xref:System.IO.Path.Combine%2A> zkombinovat cesta ke kořenové složce položky cestu kompilace.  
  
 Funkce vlastností se nemusí zobrazit v rámci hodnoty metadat.  Například  
  
 `%(Compile.FullPath.Substring(0,3))`  
  
 není povoleno.  
  
 Další informace o funkcích vlastnost, naleznete v tématu [funkce vlastností](../msbuild/property-functions.md).  
  
## <a name="see-also"></a>Viz také:  
 [Itemmetadata – element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)