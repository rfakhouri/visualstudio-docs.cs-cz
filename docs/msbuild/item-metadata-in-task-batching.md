---
title: "Metadata položek v dávkování úloh | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
- task batching [MSBuild]
- MSBuild, task batching
ms.assetid: 31e480f8-fe4d-4633-8c54-8ec498e2306d
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ee203056edb24bd2338caf1ad1b5608e4c5d3ca9
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="item-metadata-in-task-batching"></a>Metadata položek v dávkování úloh
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] má schopnost rozdělení seznamech položek do různých kategorií nebo dávek, na základě položky metadat a spuštění úlohy jednou se jednotlivých dávek. Může být matoucí pochopit přesně položky, které jsou předávány s které dávky. Toto téma obsahuje následující běžné scénáře, které zahrnují dávkování.  
  
-   Dělení seznam položek do dávek  
  
-   Dělení seznamech několik položek do dávek  
  
-   Dávkování jedna položka v čase  
  
-   Filtrování položek seznamů  
  
 Další informace o dávkování s [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], najdete v části [Batching](../msbuild/msbuild-batching.md).  
  
## <a name="dividing-an-item-list-into-batches"></a>Dělení seznam položek do dávek  
 Dávkování umožňuje rozdělení seznamu položek do různých dávek na základě položky metadat a jednotlivých dávek předat do úlohu samostatně. To je užitečné pro vytváření satelitních sestavení.  
  
 Následující příklad ukazuje, jak rozdělit seznam položek do dávek na základě položky metadat. `ExampColl` Seznamu položek je rozdělené do tří dávek na základě `Number` metadata položky. Přítomnost `%(ExampColl.Number)`v `Text` atribut informuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] , dávkování by se měla provést. `ExampColl` Seznamu položek je rozdělené do tří dávek na základě `Number` metadata a každé dávky je předána samostatně do úlohy.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
        <ExampColl Include="Item4">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item5">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item6">  
            <Number>3</Number>  
        </ExampColl>  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Number: %(ExampColl.Number) -- Items in ExampColl: @(ExampColl)"/>  
    </Target>  
  
</Project>  
```  
  
 [Úloha zprávy](../msbuild/message-task.md) úloh zobrazí následující informace:  
  
 `Number: 1 -- Items in ExampColl: Item1;Item4`  
  
 `Number: 2 -- Items in ExampColl: Item2;Item5`  
  
 `Number: 3 -- Items in ExampColl: Item3;Item6`  
  
## <a name="dividing-several-item-lists-into-batches"></a>Dělení několik položek uvádí do dávek  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] více položky seznamů lze rozdělit do dávky na základě stejné metadat. To usnadňuje rozdělení seznamech různých položek do dávky k vytvoření více sestavení. Například můžete mít seznam položek souborů .cs rozdělené do batch aplikace a batch sestavení a seznam položek zdrojových souborů, které jsou rozdělené do batch aplikace a batch sestavení. Dávkování může pak použijete k předejte tyto položky seznamů do jednu úlohu a vytvářet aplikace a sestavení.  
  
> [!NOTE]
>  Pokud seznam položek předávány do úloha neobsahuje žádné položky s metadaty odkazované, každá položka v tomto seznamu položek je předán do každou dávku.  
  
 Následující příklad ukazuje, jak rozdělit více seznamu položek do dávek na základě položky metadat. `ExampColl` a `ExampColl2` položky seznamů každý dělí do tří dávek na základě `Number` metadata položky. Přítomnost `%(Number)`v `Text` atribut informuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] , dávkování by se měla provést. `ExampColl` a `ExampColl2` položky seznamů dělí do tří dávek na základě `Number` metadata a každé dávky je předána samostatně do úlohy.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
  
        <ExampColl2 Include="Item4">  
            <Number>1</Number>  
        </ExampColl2>  
        <ExampColl2 Include="Item5">  
            <Number>2</Number>  
        </ExampColl2>  
        <ExampColl2 Include="Item6">  
            <Number>3</Number>  
        </ExampColl2>  
  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Number: %(Number) -- Items in ExampColl: @(ExampColl) ExampColl2: @(ExampColl2)"/>  
    </Target>  
  
</Project>  
```  
  
 [Úloha zprávy](../msbuild/message-task.md) úloh zobrazí následující informace:  
  
 `Number: 1 -- Items in ExampColl: Item1 ExampColl2: Item4`  
  
 `Number: 2 -- Items in ExampColl: Item2 ExampColl2: Item5`  
  
 `Number: 3 -- Items in ExampColl: Item3 ExampColl2: Item6`  
  
## <a name="batching-one-item-at-a-time"></a>Dávkování jedna položka v čase  
 Dávkování lze také provést na známá metadata položky přiřazený každá položka po vytvoření. To zaručuje, že každá položka v kolekci, bude mít některá metadata pro dávkové zpracování. `Identity` Hodnota metadat je jedinečný pro každé položky a jsou užitečné pro dělení každá položka v seznamu položek do samostatné dávky. Úplný seznam známá metadata položky, naleznete v části [Metadata známé položky](../msbuild/msbuild-well-known-item-metadata.md).  
  
 Následující příklad ukazuje, jak pro každou položku v seznamu položek jeden batch najednou. Protože `Identity` metadata hodnota každá položka je jedinečný, `ExampColl` seznamu položek je rozdělené do šesti dávek každé dávky, která obsahuje jednu položku ze seznamu položek. Přítomnost `%(Identity)`v `Text` atribut informuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] , dávkování by se měla provést.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1"/>  
        <ExampColl Include="Item2"/>  
        <ExampColl Include="Item3"/>  
        <ExampColl Include="Item4"/>  
        <ExampColl Include="Item5"/>  
        <ExampColl Include="Item6"/>  
  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Identity: "%(Identity)" -- Items in ExampColl: @(ExampColl)"/>  
    </Target>  
  
</Project>  
```  
  
 [Úloha zprávy](../msbuild/message-task.md) úloh zobrazí následující informace:  
  
```  
Identity: "Item1" -- Items in ExampColl: Item1  
Identity: "Item2" -- Items in ExampColl: Item2  
Identity: "Item3" -- Items in ExampColl: Item3  
Identity: "Item4" -- Items in ExampColl: Item4  
Identity: "Item5" -- Items in ExampColl: Item5  
Identity: "Item6" -- Items in ExampColl: Item6  
```  
  
## <a name="filtering-item-lists"></a>Obsahuje seznam filtrování položek  
 Dávkování lze filtrovat některé položky ze seznamu položek před jeho odesláním úlohu. Například na filtrování `Extension` hodnota metadata známé položky umožňuje spuštění úlohy na pouze soubory s konkrétní příponou.  
  
 Následující příklad ukazuje, jak k rozdělení seznamu položek do dávek na základě položky metadat a pak filtrovat tyto dávky, pokud jsou předávány do úlohy. `ExampColl` Seznamu položek je rozdělené do tří dávek na základě `Number` metadata položky. `Condition` Určuje atribut úlohy, která pouze dávek s `Number` položky metadat hodnotu `2` se předají do úlohy  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
        <ExampColl Include="Item4">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item5">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item6">  
            <Number>3</Number>  
        </ExampColl>  
  
    </ItemGroup>  
  
    <Target Name="Exec">  
        <Message  
            Text = "Items in ExampColl: @(ExampColl)"  
            Condition="'%(Number)'=='2'"/>  
    </Target>  
  
</Project>  
```  
  
 [Úloha zprávy](../msbuild/message-task.md) úloh zobrazí následující informace:  
  
```  
Items in ExampColl: Item2;Item5  
```  
  
## <a name="see-also"></a>Viz také  
 [Metadata známé položky](../msbuild/msbuild-well-known-item-metadata.md)   
 [Item – Element (MSBuild)](../msbuild/item-element-msbuild.md)   
 [Itemmetadata – Element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [Dávkování](../msbuild/msbuild-batching.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)