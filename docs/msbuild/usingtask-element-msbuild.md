---
title: Usingtask – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#UsingTask
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UsingTask element [MSBuild]
- <UsingTask> element [MSBuild]
ms.assetid: 20247902-9446-4a1f-8253-5c7a17e4fe43
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b97999b7a6aa56dc9be17d853c306c71a5ff290
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56645742"
---
# <a name="usingtask-element-msbuild"></a>Usingtask – element (MSBuild)
Mapuje na úkol, který se odkazuje v [úloh](../msbuild/task-element-msbuild.md) element na sestavení, které obsahuje implementaci úkolu.

 \<Projekt > \<UsingTask >

## <a name="syntax"></a>Syntaxe

```xml
<UsingTask TaskName="TaskName"
    AssemblyName = "AssemblyName"
    TaskFactory = "ClassName"
    Condition="'String A'=='String B'" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|`AssemblyName`|Buď `AssemblyName` atribut nebo `AssemblyFile` atribut je vyžadován.<br /><br /> Název sestavení, které chcete načíst. `AssemblyName` Atribut je možné zadat sestavení se silným názvem, i když není potřeba silné názvy. Pomocí tohoto atributu je ekvivalentní k načtení sestavení s použitím <xref:System.Reflection.Assembly.Load%2A> metoda v rozhraní .NET.<br /><br /> Tento atribut nelze použít, pokud `AssemblyFile` atribut se používá.|
|`AssemblyFile`|Buď `AssemblyName` nebo `AssemblyFile` atribut je vyžadován.<br /><br /> Cesta k souboru sestavení. Tento atribut je možné zadat relativní cesty nebo úplné cesty. Relativní cesty jsou relativní vzhledem k adresáři projektu soubor nebo soubor cílů kde `UsingTask` je deklarován element. Pomocí tohoto atributu je ekvivalentní k načtení sestavení s použitím <xref:System.Reflection.Assembly.LoadFrom%2A> metoda v rozhraní .NET.<br /><br /> Tento atribut nelze použít, pokud `AssemblyName` atribut se používá.|
|`TaskFactory`|Nepovinný atribut.<br /><br /> Určuje třídu v sestavení, který je zodpovědný za generování instance zadaného `Task` název.  Uživatel může také určit `TaskBody` jako podřízený prvek, který přijímá objekt pro vytváření úkolů a používá ke generování úlohy. Obsah `TaskBody` jsou specifická pro objekt pro vytváření úloh.|
|`TaskName`|Požadovaný atribut.<br /><br /> Název úkolu odkazovat ze sestavení. Pokud nejasnostem, je možné, tento atribut by měl být určen úplný obory názvů. Pokud existují nejednoznačnosti, vybere MSBuild libovolného shodu, což může vést k neočekávaným výsledkům.|
|`Condition`|Nepovinný atribut.<br /><br /> Podmínky pro hodnocení. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|[ParameterGroup](../msbuild/parametergroup-element.md)|Sada parametrů, které se zobrazují na úkol, který je generována pomocí zadané `TaskFactory`.|
|[Úloha](../msbuild/task-element-msbuild.md)|Data, která je předána `TaskFactory` k vytvoření instance úlohy.|

### <a name="parent-elements"></a>Nadřazené prvky

| Prvek | Popis |
| - | - |
| [Projekt](../msbuild/project-element-msbuild.md) | Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu. |

## <a name="remarks"></a>Poznámky
 Proměnné prostředí, vlastnosti příkazového řádku, vlastností na úrovni projektu a položek na úrovni projektu může být odkazováno v `UsingTask` prvky, které jsou zahrnuty v souboru projektu, ať už přímo nebo prostřednictvím importovaném projektu souboru. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).

> [!NOTE]
>  Vlastnosti na úrovni projektu a položky nemají význam, pokud `UsingTask` element pochází z jednoho z *.tasks* soubory, které jsou globálně zaregistrované stroji MSBuild engine. Hodnoty na úrovni projektu nejsou globální nástroji MSBuild.

 V MSBuild 4.0 pomocí úlohy je možné načíst z *.overridetask* soubory.

## <a name="example"></a>Příklad
 Následující příklad ukazuje způsob použití `UsingTask` element s `AssemblyName` atribut.

```xml
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">
       <ParameterGroup>
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>
              ...
</ParameterGroup>
       <TaskBody>
      ... Task factory-specific data ...
       </TaskBody>
</UsingTask>
```

## <a name="example"></a>Příklad
 Následující příklad ukazuje způsob použití `UsingTask` element s `AssemblyFile` atribut.

```xml
<UsingTask TaskName="Email"
              AssemblyFile="c:\myTasks\myTask.dll" />
```

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
