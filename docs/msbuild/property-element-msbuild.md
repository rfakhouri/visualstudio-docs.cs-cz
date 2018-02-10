---
title: "Property – Element (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Property> Element [MSBuild]
- Property Element [MSBuild]
ms.assetid: 69ab08ab-3e76-41dd-a01b-49aa1d2e0cac
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9a71cb5d218c7c980e23f2fd9e87df2b614aece5
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="property-element-msbuild"></a>Property – element (MSBuild)
Obsahuje uživatelské jméno definované vlastnosti a hodnotu. Každou vlastnost v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu musí být zadány jako podřízenou `PropertyGroup` elementu.  

 \<Project>  
 \<PropertyGroup>  

## <a name="syntax"></a>Syntaxe  

```  
<Property Condition="'String A' == 'String B'">  
    Property Value  
</Property>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené elementy  
 Žádné  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Element seskupení pro vlastnosti.|  

## <a name="text-value"></a>Textová hodnota  
 Textová hodnota je volitelná.  

 Tento text určuje hodnotu vlastnosti a pravděpodobně obsahuje kód XML.  

## <a name="remarks"></a>Poznámky  
 Názvy vlastností jsou omezeny na pouze znaků ASCII. Hodnoty vlastností se odkazuje v projektu tím, že název vlastnosti mezi "`$(`"a"`)`". Například `$(builddir)\classes` by odkazující na "build\classes", pokud `builddir` vlastnost měl hodnotu `build`. Další informace o vlastnostech najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  

## <a name="example"></a>Příklad  
 Následující kód nastaví `Optimization` vlastnost `false` a `DefaultVersion` vlastnost `1.0` Pokud `Version` vlastnost je prázdná.  

```xml  
<PropertyGroup>  
    <Optimization>false</Optimization>  
    <DefaultVersion Condition="'$(Version)' == ''" >1.0</DefaultVersion>  
</PropertyGroup>  
```  

## <a name="see-also"></a>Viz také
[Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
