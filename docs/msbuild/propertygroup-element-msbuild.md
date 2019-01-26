---
title: PropertyGroup – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ae63602b1892bca722ae8eb5e2052c103597fb6e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941186"
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup – element (MSBuild)
Obsahuje sadu uživatelem definované [vlastnost](../msbuild/property-element-msbuild.md) elementy. Každý `Property` prvku použitého při [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekt musí být podřízeným `PropertyGroup` elementu.  

 \<Project>  
 \<PropertyGroup>  

## <a name="syntax"></a>Syntaxe  

```xml  
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

### <a name="child-elements"></a>Podřízené prvky  

|Prvek|Popis|  
|-------------|-----------------|  
|[Vlastnost](../msbuild/property-element-msbuild.md)|Volitelný element.<br /><br /> Název definované vlastnosti uživatele, který obsahuje hodnotu vlastnosti. Může být nula nebo více *vlastnost* prvky `PropertyGroup` elementu.|  

### <a name="parent-elements"></a>Nadřazené prvky  

| Prvek | Popis |
| - | - |
| [Projekt](../msbuild/project-element-msbuild.md) | Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu. |

## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak nastavit vlastnosti na základě podmínky. V tomto příkladu Pokud hodnota `CompileConfig` vlastnost je `DEBUG`, `Optimization`, `Obfuscate`, a `OutputPath` vlastnosti uvnitř `PropertyGroup` element jsou nastavené.  

```xml  
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >  
    <Optimization>false</Optimization>  
    <Obfuscate>false</Obfuscate>  
    <OutputPath>$(OutputPath)\debug</OutputPath>  
</PropertyGroup>  
```  

## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)  
 [Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)
