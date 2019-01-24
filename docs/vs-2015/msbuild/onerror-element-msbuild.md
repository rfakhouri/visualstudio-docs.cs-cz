---
title: Onerror – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
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
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 70430172c734a37259f7dc80fdfa440d9d0ee471
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54766288"
---
# <a name="onerror-element-msbuild"></a>OnError – element (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Způsobí, že jeden nebo více cílů ke spuštění, pokud `ContinueOnError` atribut je `false` neúspěšné úlohy.  
  
 \<Project>  
 \<Cíl >  
 \<Onerror – >  
  
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
|`ExecuteTargets`|Požadovaný atribut.<br /><br /> Cílů ke spuštění neúspěšné úlohy. Několik cílů oddělte středníky. Několik cílů jsou spuštěny v uvedeném pořadí.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Cíl](../msbuild/target-element-msbuild.md)|Prvek kontejneru pro [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] úlohy.|  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] Spustí `OnError` element, pokud jeden z `Target` elementu úlohy nezdaří a zobrazí se `ContinueOnError` atribut nastaven na `ErrorAndStop` (nebo `false`). Pokud úloha selže, cíle zadané v `ExecuteTargets` atribut je proveden. Pokud existuje více než jeden `OnError` element v cíli, `OnError` prvky jsou spouštěny postupně, pokud se úloha nezdaří.  
  
 Informace o tom, `ContinueOnError` atributu naleznete v tématu [Task – Element (MSBuild)](../msbuild/task-element-msbuild.md). Informace o cílech naleznete v tématu [cíle](../msbuild/msbuild-targets.md).  
  
## <a name="example"></a>Příklad  
 Následující kód se provádí `TaskOne` a `TaskTwo` úlohy. Pokud `TaskOne` selže, [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] vyhodnotí `OnError` elementu a spustí `OtherTarget` cíl.  
  
```  
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
