---
title: "Parameter – Element | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
- xml
helpviewer_keywords:
- Parameter element [MSBuild]
- <Parameter> element [MSBuild]
ms.assetid: b273afff-b500-4e97-8cfd-31f39fa64a51
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 39dd727eee6f9af2f60410c4dbfc9daa9ea805a2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="parameter-element"></a>Parameter – Element
Obsahuje informace o určitém parametru pro úlohu, která je generován `UsingTask``TaskFactory`.  Název elementu je název parametru.  Chcete-li – další informace, najdete v tématu [usingtask – Element (MSBuild)](../msbuild/usingtask-element-msbuild.md).  

 \<Projekt >  
 \<Usingtask – >  
 \<ParameterGroup >  
 \<Parametr >  

## <a name="syntax"></a>Syntaxe  

```  
<ParameterGroup ParameterType="SystemType"  
    Output="true/false"  
    Required="true/false" />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`ParameterType`|Nepovinný atribut.<br /><br /> Typ formátu .NET parametru, například "System.String".|  
|`Output`|Volitelný logický atribut.<br /><br /> Pokud `true`, tento parametr je výstupní parametr pro úlohu. Výchozí hodnota je `false`.|  
|`Required`|Volitelný logický atribut.<br /><br /> Pokud `true`, tento parametr je povinný parametr pro úlohu. Výchozí hodnota je `false`.|  

### <a name="child-elements"></a>Podřízené elementy  
 Žádné  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|Obsahuje volitelný seznam parametrů, které bude k dispozici na úloha, která je generován `UsingTask``TaskFactory`.|  

## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `Parameter` elementu.  

```xml  
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">  
       <ParameterGroup>  
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>  
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>  
             ...  
</ParameterGroup>  
       <TaskBody Evaluate="true">  
      ... Task factory-specific data ...  
       </TaskBody>  
</UsingTask>  
```  

## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
