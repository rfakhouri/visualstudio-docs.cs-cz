---
title: "Dávkování nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
ms.assetid: d35c085b-27b8-49d7-b6f8-8f2f3a0eec38
caps.latest.revision: "9"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: e2ad60b0b0f98cee23de911a8ca7cf2e5d43b364
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-batching"></a>Dávkování nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]má schopnost rozdělení seznamech položek do různých kategorií nebo dávek, na základě položky metadat a spusťte cíl a úloh s jednou jednotlivých dávek.  
  
## <a name="task-batching"></a>Dávkování úloh  
 Dávkování úloh, můžete zjednodušit tím, že poskytuje způsob, jak rozdělení seznamech položek do různých dávek a každý z těchto dávek samostatně předat do úlohu soubory projektu. To znamená, že soubor projektu pouze musí mít úlohu a jeho atributy deklarován jednou, i když můžete spustit několikrát.  
  
 Určíte, že chcete [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k provedení dávkování s úlohu pomocí %(*ItemMetaDataName*) zápis v jeden z atributů úloh. Následující příklad rozdělí `Example` na základě seznamu položek do dávek `Color` hodnota metadata položky a předává dávek k `MyTask` úloh samostatně.  
  
> [!NOTE]
>  Pokud jste neodkazují na seznamu položek jinde v atributech úloh nebo může být nejednoznačný název metadat, můžete použít %(*ItemCollection.ItemMetaDataName*) zápis k plnému určení hodnotu položky metadat pro dávkové zpracování.  
  
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
  
 Dávkování konkrétnější příklady najdete v tématu [Metadata položek v dávkování úloh](../msbuild/item-metadata-in-task-batching.md).  
  
## <a name="target-batching"></a>Dávkování cíle  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]kontroluje, pokud vstupy a výstupy cíl jsou aktuální před jeho spuštěním cíl. Pokud jsou aktuální vstupy a výstupy, cíl se přeskočí. Pokud úloha uvnitř cíl používá dávkování, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] je potřeba určit, zda je aktuální vstupy a výstupy pro jednotlivé skupiny položek. Jinak hodnota cíle se spustí pokaždé, když je dosaženo.  
  
 Následující příklad ukazuje `Target` elementu, který obsahuje `Outputs` atribut s %(*ItemMetaDataName*) zápis. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]bude dělit `Example` na základě seznamu položek do dávek `Color` položky metadat a analyzovat časová razítka výstupních souborů pro každou dávku. Pokud výstupy z dávky nejsou aktuální, cíl běží. Cíl, jinak se přeskočí.  
  
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
  
 Další příklad dávkování cíle, najdete v části [Metadata položek v dávkování cíle](../msbuild/item-metadata-in-target-batching.md).  
  
## <a name="property-functions-using-metadata"></a>Funkce vlastností pomocí metadat  
 Dávkování lze řídit pomocí funkce vlastností, které zahrnují metadata. Například  
  
 `$([System.IO.Path]::Combine($(RootPath),%(Compile.Identity)))`  
  
 používá <xref:System.IO.Path.Combine%2A> kombinovat kořenové složky s cestou položky kompilace.  
  
 Funkce vlastností se nemůže nacházet v rámci hodnoty metadat.  Například  
  
 `%(Compile.FullPath.Substring(0,3))`  
  
 není povoleno.  
  
 Další informace o funkcích vlastnost najdete v tématu [funkce vlastností](../msbuild/property-functions.md).  
  
## <a name="see-also"></a>Viz také  
 [Itemmetadata – Element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)