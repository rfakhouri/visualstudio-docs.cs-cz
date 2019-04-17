---
title: Parametergroup – Element | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ParameterGroup> element [MSBuild]
- ParameterGroup element [MSBuild]
ms.assetid: c3275e69-a427-4889-bc1d-51bff2c285fa
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5f4faa9038a5931dec376903f166301f27f00b37
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59656229"
---
# <a name="parametergroup-element"></a>ParameterGroup – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Obsahuje volitelný seznam parametrů, které bude k dispozici na na úkol, který je generován `UsingTask``TaskFactory`. Další informace najdete v tématu [usingtask – Element (MSBuild)](../msbuild/usingtask-element-msbuild.md).  
  
 \<Project>  
 \<Usingtask – >  
 \<ParameterGroup>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ParameterGroup />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Parametr](../msbuild/parameter-element.md)|Obsahuje informace o určitý parametr u úkolu, který je generován `UsingTask``TaskFactory`. Název elementu je název parametru.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Usingtask –](../msbuild/usingtask-element-msbuild.md)|Poskytuje způsob, jak zaregistrovat úlohy v [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]. Může být nula nebo více `UsingTask` prvky v projektu.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `ParameterGroup` elementu.  
  
```  
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
