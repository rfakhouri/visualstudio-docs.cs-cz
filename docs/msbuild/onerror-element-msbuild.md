---
title: "OnError – Element (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#OnError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- OnError Element [MSBuild]
- <OnError Element [MSBuild]
ms.assetid: 765767d3-ecb7-4cd9-ba1e-d9468964dddc
caps.latest.revision: "14"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 1c0238bb7a525166f69a59b0af5d08db5286a5f8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="onerror-element-msbuild"></a>OnError – element (MSBuild)
Způsobí, že jeden nebo více cílů provést, pokud `ContinueOnError` atribut je `false` pro nezdařené úlohy.  

 \<Projekt >  
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
|[Cíl](../msbuild/target-element-msbuild.md)|Element kontejneru pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy.|  

## <a name="remarks"></a>Poznámky  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]Spustí `OnError` elementu, pokud jeden z `Target` elementu úlohy nezdaří a zobrazí se `ContinueOnError` atribut nastaven na `ErrorAndStop` (nebo `false`). Pokud úloha selže, cíle zadané v `ExecuteTargets` atribut se spustí. Pokud je více než jedna `OnError` element na cíli, `OnError` elementy jsou prováděny postupně, pokud úloha selže.  

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
