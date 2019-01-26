---
title: Output – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Output
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Output> Element [MSBuild]
- Output Element [MSBuild]
ms.assetid: 34bc7cd1-efd3-4b57-b691-4584eeb6a0e9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dad60ce9352e85208a3548f6bcb0dabc8f63bee0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54998492"
---
# <a name="output-element-msbuild"></a>Output – element (MSBuild)
Úložiště úlohy výstupní hodnoty v položek a vlastností.  

 \<Project>  
 \<Cíl >  
 \<Úloha >  
 \<Výstup >  

## <a name="syntax"></a>Syntaxe  

```xml  
<Output TaskParameter="Parameter"  
    PropertyName="PropertyName"   
    Condition = "'String A' == 'String B'" />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`TaskParameter`|Požadovaný atribut.<br /><br /> Název úkolu výstupní parametr.|  
|`PropertyName`|Buď `PropertyName` nebo `ItemName` atribut je vyžadován.<br /><br /> Vlastnost, která obdrží úkol výstupní hodnota parametru. Váš projekt pak může odkazovat na vlastnost $ (\<PropertyName >) syntaxe. Název této vlastnosti může být buď nový název vlastnosti nebo název, který je již definován v projektu.<br /><br /> Tento atribut nedá použít, pokud `ItemName` se také používá.|  
|`ItemName`|Buď `PropertyName` nebo `ItemName` atribut je vyžadován.<br /><br /> Hodnota parametru výstupní položku, která obdrží úkol. Váš projekt pak může odkazovat položka @(\<název položky >) syntaxe. Název položky může být buď název nové položky nebo název, který je již definován v projektu. Když se název položky je existující položku, hodnoty výstupních parametrů se přidají do existující položku. <br /><br /> Tento atribut nedá použít, pokud `PropertyName` se také používá.|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené prvky  
 Žádné  

### <a name="parent-elements"></a>Nadřazené prvky  

| Prvek | Popis |
| - | - |
| [Úloha](../msbuild/task-element-msbuild.md) | Vytvoří a spustí instanci [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úloh. |

## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `Csc` úloh se spouští uvnitř `Target` elementu. Mimo rozsah v tomto příkladu jsou deklarovány položek a vlastností předat parametry úlohy. Hodnota z výstupního parametru `OutputAssembly` je uložen v `FinalAssemblyName` položky a hodnotu z výstupního parametru `BuildSucceeded` je uložen v `BuildWorked` vlastnost. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  

```xml  
<Target Name="Compile" DependsOnTargets="Resources">  
    <Csc  Sources="@(CSFile)"  
            TargetType="library"  
            Resources="@(CompiledResources)"  
            EmitDebugInformation="$(includeDebugInformation)"  
            References="@(Reference)"  
            DebugType="$(debuggingType)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).dll" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
        <Output TaskParameter="BuildSucceeded"  
                  PropertyName="BuildWorked" />  
    </Csc>  
</Target>  
```  

## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)
