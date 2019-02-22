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
ms.openlocfilehash: fc410948f3869de5ca3059cba703e5381f93d7eb
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56603572"
---
# <a name="parameter-element"></a>Parameter – element
Obsahuje informace o určitý parametr u úkolu, který je generován `UsingTask` `TaskFactory`.  Název elementu je název parametru.  Další informace najdete v tématu [usingtask – element (MSBuild)](../msbuild/usingtask-element-msbuild.md).

 \<Project> \<UsingTask> \<ParameterGroup> \<Parameter>

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
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
