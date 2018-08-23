---
title: PropertyGroup – Element (MSBuild) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a89a11de811eda28abc1ef8463ae29cbd81825a1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675391"
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup – element (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [PropertyGroup – Element (MSBuild)](https://docs.microsoft.com/visualstudio/msbuild/propertygroup-element-msbuild).  
  
  
Obsahuje sadu uživatelem definované [vlastnost](../msbuild/property-element-msbuild.md) elementy. Každý `Property` prvku použitého při [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projekt musí být podřízeným `PropertyGroup` elementu.  
  
 \<Project>  
 \<PropertyGroup >  
  
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
|[Vlastnost](../msbuild/property-element-msbuild.md)|Volitelný element.<br /><br /> Název definované vlastnosti uživatele, který obsahuje hodnotu vlastnosti. Může být nula nebo více *vlastnost* prvky `PropertyGroup` elementu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] souboru projektu.|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak nastavit vlastnosti na základě podmínky. V tomto příkladu Pokud hodnota `CompileConfig` vlastnost je `DEBUG`, `Optimization`, `Obfuscate`, a `OutputPath` vlastnosti uvnitř `PropertyGroup` element jsou nastavené.  
  
```  
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >  
    <Optimization>false</Optimization>  
    <Obfuscate>false</Obfuscate>  
    <OutputPath>$(OutputPath)\debug</OutputPath>  
</PropertyGroup>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)  
 [Vlastnosti nástroje MSBuild](msbuild-properties1.md)



