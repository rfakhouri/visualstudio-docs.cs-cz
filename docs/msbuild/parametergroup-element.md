---
title: Parametergroup – Element | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ParameterGroup> element [MSBuild]
- ParameterGroup element [MSBuild]
ms.assetid: c3275e69-a427-4889-bc1d-51bff2c285fa
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a531073ba6f2f55272b719a116caad724d29e53
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916160"
---
# <a name="parametergroup-element"></a>Parametergroup – element
Obsahuje volitelný seznam parametrů, které bude k dispozici na na úkol, který je generován `UsingTask` `TaskFactory`. Další informace najdete v tématu [usingtask – element (MSBuild)](../msbuild/usingtask-element-msbuild.md).  

 \<Project>  
 \<Usingtask – >  
 \<Parametergroup – >  

## <a name="syntax"></a>Syntaxe  

```xml  
<ParameterGroup />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  
 Žádné  

### <a name="child-elements"></a>Podřízené prvky  

|Prvek|Popis|  
|-------------|-----------------|  
|[Parametr](../msbuild/parameter-element.md)|Obsahuje informace o určitý parametr u úkolu, který je generován `UsingTask` `TaskFactory`. Název elementu je název parametru.|  

### <a name="parent-elements"></a>Nadřazené prvky  

| Prvek | Popis |
| - | - |
| [Usingtask –](../msbuild/usingtask-element-msbuild.md) | Poskytuje způsob, jak zaregistrovat úlohy v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Může být nula nebo více `UsingTask` prvky v projektu. |

## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `ParameterGroup` elementu.  

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

## <a name="see-also"></a>Viz také:  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
