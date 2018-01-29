---
title: "SDK – Element (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 01/25/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Project
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Sdk element [MSBuild]
- <Sdk> element [MSBuild]
author: jeffkl
ms.author: jeffkl
manager: angerlic
ms.workload:
- multiple
ms.openlocfilehash: 34db4807b3ab373c2a5b3c32fd9ef310263c3f7c
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="sdk-element-msbuild"></a>SDK – Element (MSBuild)
Odkazy [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu sady SDK.  

 \<Project>  
 \<Sdk>  


## <a name="syntax"></a>Syntaxe  

```  
<Sdk Name="My.Custom.Sdk"
     Version="1.0.0" />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadovaný atribut.<br /><br /> Název projektu sady SDK.|  
|`Version`|Nepovinný atribut.<br /><br /> Verze projektu sady SDK|  

### <a name="child-elements"></a>Podřízené elementy  
 Žádné

### <a name="parent-elements"></a>Nadřazené elementy  
 |Prvek|Popis|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.|  

## <a name="see-also"></a>Viz také  
 [Postupy: referenční projektu MSBuild SDK](../msbuild/how-to-use-project-sdk.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)
