---
title: OnError – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#OnError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- OnError Element [MSBuild]
- <OnError Element [MSBuild]
ms.assetid: 765767d3-ecb7-4cd9-ba1e-d9468964dddc
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f70588c512716cac854bab446c7a7d695e392a28
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="onerror-element-msbuild"></a>OnError – element (MSBuild)
Způsobí, že jeden nebo více cílů provést, pokud `ContinueOnError` atribut je `false` pro nezdařené úlohy.  

 \<Project>  
 \<Cíl >  
 \<OnError >  

## <a name="syntax"></a>Syntaxe  

```  
<OnError ExecuteTargets="TargetName"  
    Condition="'String A'=='String B'" />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  
|`ExecuteTargets`|Požadovaný atribut.<br /><br /> Cíle provést, pokud se úloha nezdaří. Více cílů oddělte středníky. Více cílů jsou provedeny v uvedeném pořadí.|  

### <a name="child-elements"></a>Podřízené elementy  
 Žádné  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[cíl](../msbuild/target-element-msbuild.md)|Element kontejneru pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy.|  

## <a name="remarks"></a>Poznámky  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Spustí `OnError` elementu, pokud jeden z `Target` elementu úlohy nezdaří a zobrazí se `ContinueOnError` atribut nastaven na `ErrorAndStop` (nebo `false`). Pokud úloha selže, cíle zadané v `ExecuteTargets` atribut se spustí. Pokud je více než jedna `OnError` element na cíli, `OnError` elementy jsou prováděny postupně, pokud úloha selže.  

 Informace o `ContinueOnError` atributů najdete v tématu [Task – Element (MSBuild)](../msbuild/task-element-msbuild.md). Informace o cílech najdete v tématu [cíle](../msbuild/msbuild-targets.md).  

## <a name="example"></a>Příklad  
 Následující kód spustí `TaskOne` a `TaskTwo` úlohy. Pokud `TaskOne` selže, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vyhodnotí `OnError` elementu a spouští `OtherTarget` cíl.  

```xml  
<Target Name="ThisTarget">  
    <TaskOne ContinueOnError="ErrorAndStop">  
    </TaskOne>  
    <TaskTwo>  
    </TaskTwo>  
    <OnError ExecuteTargets="OtherTarget" />  
</Target>  
```  

## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Cíle](../msbuild/msbuild-targets.md)
