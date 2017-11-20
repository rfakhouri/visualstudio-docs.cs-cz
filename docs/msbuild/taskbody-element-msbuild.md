---
title: "Taskbody – Element (MSBuild) | Microsoft Docs"
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
helpviewer_keywords:
- TaskBody element [MSBuild]
- <TaskBody> element [MSBuild]
ms.assetid: 49d8741b-f1ea-4470-94fd-a1ac27341a6a
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: e2f0f502a206a321bd581054eecef0b75485809e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="taskbody-element-msbuild"></a>TaskBody – element (MSBuild)
Obsahuje data, která je předána `UsingTask``TaskFactory`. Další informace najdete v tématu [usingtask – Element (MSBuild)](../msbuild/usingtask-element-msbuild.md).  

 \<Projekt >  
 \<Usingtask – >  
 \<Taskbody – >  

## <a name="syntax"></a>Syntaxe  

```  
<TaskBody Evaluate="true/false" />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Evaluate`|Volitelný logický atribut.<br /><br /> Pokud `true`, MSBuild vyhodnocuje všechny vnitřní elementy a rozbalí položky a vlastnosti před odesláním informací `TaskFactory` při vytvoření instance úlohy.|  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|Data|Text mezi `TaskBody` značky se odesílají do typu verbatim `TaskFactory`.|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Usingtask –](../msbuild/usingtask-element-msbuild.md)|Poskytuje způsob, jak zaregistrovat úlohy v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Může být nula nebo více `UsingTask` elementy v projektu.|  

## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `TaskBody` element s `Evaluate` atribut.  

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
