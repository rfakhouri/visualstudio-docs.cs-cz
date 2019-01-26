---
title: ItemDefinitionGroup – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ItemDefinitionGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemDefinitionGroup Element [MSBuild]
- <ItemDefinitionGroup> Element [MSBuild]
ms.assetid: 4e9fb04b-5148-4ae5-a394-42861dd62371
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9faf5d0b242f81726dc2e0b8fe4a955db31938a2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54918417"
---
# <a name="itemdefinitiongroup-element-msbuild"></a>ItemDefinitionGroup – element (MSBuild)
`ItemDefinitionGroup` Prvek umožňuje definovat sadu definice položek, které jsou hodnoty metadat, které se použijí u všech položek v projektu, ve výchozím nastavení. ItemDefinitionGroup – nahrazuje nutnost používat [createitem – úloha](../msbuild/createitem-task.md) a [CreateProperty – úloha](../msbuild/createproperty-task.md). Další informace najdete v tématu [definice položek](../msbuild/item-definitions.md).  

 \<Project>  
 \<ItemDefinitionGroup>  

## <a name="syntax"></a>Syntaxe  

```xml  
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

### <a name="child-elements"></a>Podřízené prvky  

|Prvek|Popis|  
|-------------|-----------------|  
|[Položka](../msbuild/item-element-msbuild.md)|Definuje vstupy pro proces sestavení. Může být nula nebo více `Item` prvky `ItemDefinitionGroup`.|  

### <a name="parent-elements"></a>Nadřazené prvky  

| Prvek | Popis |
| - | - |
| [Projekt](../msbuild/project-element-msbuild.md) | Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu. |

## <a name="example"></a>Příklad  
 Následující příklad kódu definuje dvě položky metadat, stiskem n, m v ItemDefinitionGroup –. V tomto příkladu je použít výchozí metadat "m" k položce "i", protože metadata "m" není explicitně určené položky "i". Výchozí metadat "n" však není použít k položce "i", protože metadata "n" je již definován položky "i".  

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

## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Položky](../msbuild/msbuild-items.md)
