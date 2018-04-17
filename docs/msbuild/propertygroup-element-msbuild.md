---
title: PropertyGroup – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#PropertyGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <PropertyGroup> element [MSBuild]
- PropertyGroup element [MSBuild]
ms.assetid: ff1e6c68-b9a1-4263-a1ce-dc3b829a64d4
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9958335335efc007a7f2410612929fd3ac8bdca4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup – element (MSBuild)
Obsahuje sadu uživatelem definované [vlastnost](../msbuild/property-element-msbuild.md) elementy. Každý `Property` element používány [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu musí být podřízenou `PropertyGroup` element.  

 \<Project>  
 \<PropertyGroup – >  

## <a name="syntax"></a>Syntaxe  

```  
<PropertyGroup Condition="'String A' == 'String B'">  
    <Property1>...</Property1>  
    <Property2>...</Property2>  
</PropertyGroup>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|Podmínka|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Vlastnost](../msbuild/property-element-msbuild.md)|Volitelný element.<br /><br /> Definované vlastnosti jméno uživatele, který obsahuje hodnoty vlastnosti. Může být nula nebo více *vlastnost* elementů v `PropertyGroup` elementu.|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.|  

## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak nastavit vlastnosti na základě podmínky. V tomto příkladu Pokud hodnota `CompileConfig` vlastnost je `DEBUG`, `Optimization`, `Obfuscate`, a `OutputPath` vlastnosti uvnitř `PropertyGroup` element jsou nastavené.  

```xml  
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >  
    <Optimization>false</Optimization>  
    <Obfuscate>false</Obfuscate>  
    <OutputPath>$(OutputPath)\debug</OutputPath>  
</PropertyGroup>  
```  

## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)  
 [Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)
