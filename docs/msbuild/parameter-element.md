---
title: Parameter – Element | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83f713382b0f767d966276807b1d10fac39c4bcd
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54982736"
---
# <a name="parameter-element"></a>Parameter – element
Obsahuje informace o určitý parametr u úkolu, který je generován `UsingTask` `TaskFactory`.  Název elementu je název parametru.  Další informace najdete v tématu [usingtask – element (MSBuild)](../msbuild/usingtask-element-msbuild.md).  

 \<Project>  
 \<Usingtask – >  
 \<ParameterGroup>  
 \<Parametr >  

## <a name="syntax"></a>Syntaxe  

```xml  
<ParameterGroup ParameterType="SystemType"  
    Output="true/false"  
    Required="true/false" />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`ParameterType`|Nepovinný atribut.<br /><br /> Typ formátu .NET parametru, například `System.String`.|  
|`Output`|Volitelný logický atribut.<br /><br /> Pokud `true`, tento parametr je výstupní parametr pro úlohu. Výchozí hodnota je `false`.|  
|`Required`|Volitelný logický atribut.<br /><br /> Pokud `true`, tento parametr je povinný parametr pro úlohu. Výchozí hodnota je `false`.|  

### <a name="child-elements"></a>Podřízené prvky  
 Žádné  

### <a name="parent-elements"></a>Nadřazené prvky  

|Prvek|Popis|  
|-------------|-----------------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|Obsahuje volitelný seznam parametrů, které bude k dispozici na na úkol, který je generován `UsingTask` `TaskFactory`.|  

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

## <a name="see-also"></a>Viz také:  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
