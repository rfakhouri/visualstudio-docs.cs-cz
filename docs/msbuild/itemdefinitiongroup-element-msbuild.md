---
title: "ItemDefinitionGroup – Element (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#ItemDefinitionGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemDefinitionGroup Element [MSBuild]
- <ItemDefinitionGroup> Element [MSBuild]
ms.assetid: 4e9fb04b-5148-4ae5-a394-42861dd62371
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1a8444c63d7c025c04f212901e82cce6d5cf24da
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="itemdefinitiongroup-element-msbuild"></a>ItemDefinitionGroup – element (MSBuild)
`ItemDefinitionGroup` Vám umožňuje definovat sadu definice položek, které jsou hodnoty metadata, která se použijí pro všechny položky v projektu, ve výchozím nastavení. ItemDefinitionGroup nahrazuje nutnost používat [createitem – úloha](../msbuild/createitem-task.md) a [CreateProperty – úloha](../msbuild/createproperty-task.md). Další informace najdete v tématu [definice položek](../msbuild/item-definitions.md).  

 \<Projekt >  
 \<ItemDefinitionGroup >  

## <a name="syntax"></a>Syntaxe  

```  
<ItemDefinitionGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemDefinitionGroup>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Condition`|Nepovinný atribut. Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Položka](../msbuild/item-element-msbuild.md)|Definuje vstupní hodnoty pro proces sestavení. Může být nula nebo více `Item` elementů v `ItemDefinitionGroup`.|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.|  

## <a name="example"></a>Příklad  
 Následující příklad kódu definuje dvě položky metadat, m a n, ItemDefinitionGroup. V tomto příkladu je výchozí metadata "m" použít na položku "i", protože metadata "m" nejsou výslovně definované položkou "i". Výchozí metadata "n" však není použita na položku "i", protože metadata "n" je již definována položka "i".  

```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemDefinitionGroup>  
        <i>  
            <m>m1</m>  
            <n>n1</n>  
        </i>        
    </ItemDefinitionGroup>  
    <ItemGroup>  
        <i Include="a">  
            <o>o1</o>  
            <n>n2</n>  
        </i>  
    </ItemGroup>  
    ...  
</Project>  
```  

## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Položky](../msbuild/msbuild-items.md)
