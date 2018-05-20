---
title: Usingtask – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 486ca90ac2a8a4b3b289b0896e2cd81239502558
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="usingtask-element-msbuild"></a>UsingTask – element (MSBuild)
Mapuje úloha, která odkazuje [úloh](../msbuild/task-element-msbuild.md) element na sestavení, které obsahuje implementaci úloh.  

 \<Project>  
 \<Usingtask – >  

## <a name="syntax"></a>Syntaxe  

```  
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
|`AssemblyName`|Buď `AssemblyName` atribut nebo `AssemblyFile` atribut je požadován.<br /><br /> Název sestavení, které chcete načíst. `AssemblyName` Atribut přijímá sestavení se silným názvem, i když silné názvy není potřeba. Pomocí tohoto atributu je ekvivalentní načítání sestavení pomocí <xref:System.Reflection.Assembly.Load%2A> metoda v rozhraní .NET.<br /><br /> Tento atribut nelze použít, pokud `AssemblyFile` je použit atribut.|  
|`AssemblyFile`|Buď `AssemblyName` nebo `AssemblyFile` atribut je požadován.<br /><br /> Cesta k souboru sestavení. Tento atribut přijme úplné cesty nebo relativní cesty. Relativní cesty jsou relativní vzhledem k adresáři projektu soubor nebo soubor cíle kde `UsingTask` je deklarovaný element. Pomocí tohoto atributu je ekvivalentní načítání sestavení pomocí <xref:System.Reflection.Assembly.LoadFrom%2A> metoda v rozhraní .NET.<br /><br /> Tento atribut nelze použít, pokud `AssemblyName` je použit atribut.|  
|`TaskFactory`|Nepovinný atribut.<br /><br /> Určuje třídu v sestavení, která je zodpovědná za generování instance zadaného `Task` název.  Uživatel může také zadat `TaskBody` jako podřízený element, který objekt pro vytváření úloh obdrží a používá ke generování úlohu. Obsah `TaskBody` jsou specifické pro vytváření úloh.|  
|`TaskName`|Požadovaný atribut.<br /><br /> Název úlohy na ni mohli odkazovat ze sestavení. Pokud nejednoznačnosti je možné, tento atribut by měl být určen úplné obory názvů. Pokud existují nejednoznačnosti, MSBuild zvolí libovolný shodu, která by mohla vést k neočekávaným výsledkům.|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínky pro vyhodnocení. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|Sadu parametrů, které se zobrazují na úloha, která je generována pomocí zadané `TaskFactory`.|  
|[Úloha](../msbuild/task-element-msbuild.md)|Data, která je předána `TaskFactory` ke generování instance úlohy.|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.|  

## <a name="remarks"></a>Poznámky  
 Proměnné prostředí, vlastnosti příkazového řádku, vlastnosti na úrovni projektu a úrovni projektu položky může být odkazováno v `UsingTask` elementy, které jsou zahrnuty v souboru projektu, buď přímo nebo prostřednictvím projektu importovaný soubor. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  

> [!NOTE]
>  Vlastnosti na úrovni projektu a položky mít žádný význam, pokud `UsingTask` element pochází z jednoho z .tasks soubory, které jsou globálně registrované s modulem MSBuild. Hodnoty úrovni projektu nejsou globální pro MSBuild.  

 V nástroji MSBuild 4.0 pomocí úloh lze načíst z .overridetask souborů.  

## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `UsingTask` element s `AssemblyName` atribut.  

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
 Následující příklad ukazuje, jak používat `UsingTask` element s `AssemblyFile` atribut.  

```xml  
<UsingTask TaskName="Email"  
              AssemblyFile="c:\myTasks\myTask.dll" />  
```  

## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
