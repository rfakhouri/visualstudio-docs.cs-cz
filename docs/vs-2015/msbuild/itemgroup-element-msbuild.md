---
title: Itemgroup – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ItemGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemGroup element [MSBuild]
- <ItemGroup> element [MSBuild]
ms.assetid: aac894e3-a9f1-4bbc-a796-6ef07001f35b
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 20c22e0ea2ef05c108ebe564b186ede2a02f9dfe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68162422"
---
# <a name="itemgroup-element-msbuild"></a>ItemGroup – element (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Obsahuje sadu uživatelem definované [položky](../msbuild/item-element-msbuild.md) elementy. Každá položka používané [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projektu musí být zadán jako podřízený objekt `ItemGroup` element.  
  
 \<Project>  
 \<ItemGroup>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ItemGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemGroup>  
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
|[Položka](../msbuild/item-element-msbuild.md)|Definuje vstupy pro proces sestavení. Může být nula nebo více `Item` prvky `ItemGroup`.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] souboru projektu.|  
|[Cíl](../msbuild/target-element-msbuild.md)|Od verze rozhraní .NET Framework 3.5 `ItemGroup` element může být použit uvnitř `Target` elementu. Další informace najdete v tématu [cíle](../msbuild/msbuild-targets.md).|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje kolekce uživatelem definovanou položku katalogu `Res` a `CodeFiles` deklarované uvnitř `ItemGroup` elementu. Všechny položky v `Res` položky kolekce obsahuje definovaný uživatelem podřízený [itemmetadata –](../msbuild/itemmetadata-element-msbuild.md) elementu.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Res Include = "Strings.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include = "Dialogs.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
  
        <CodeFiles Include="**\*.cs" Exclude="**\generated\*.cs" />  
        <CodeFiles Include="..\..\Resources\Constants.cs" />  
    </ItemGroup>  
...  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Položky](../msbuild/msbuild-items.md)   
 [Společné položky projektu nástroje MSBuild](../msbuild/common-msbuild-project-items.md)
