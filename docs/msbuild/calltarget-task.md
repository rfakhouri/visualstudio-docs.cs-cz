---
title: Calltarget – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CallTarget task [MSBuild]
- MSBuild, CallTarget task
ms.assetid: bb1fe2c4-4383-436f-8326-c24cc4a46150
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eb209524f5e116441743521591752e5f4d64adc6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="calltarget-task"></a>CallTarget – úloha
Vyvolá zadanou cílů v rámci souboru projektu.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `CallTarget` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`RunEachTargetSeparately`|Volitelné `Boolean` vstupní parametr.<br /><br /> Pokud `true`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] modul je vyvolána jedenkrát za cíl. Pokud `false`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] modul je jednou volána k sestavení všechny cíle. Výchozí hodnota je `false`.|  
|`TargetOutputs`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje výstupy všech předdefinovaných cílů.|  
|`Targets`|Volitelné `String[]` parametr.<br /><br /> Určuje cílový nebo cíle k sestavení.|  
|`UseResultsCache`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, výsledky uložené v mezipaměti je vrácena, pokud je k dispozici.<br /><br /> **Poznámka:** se spustí při MSBuild – úloha, její výstup se uloží do mezipaměti v oboru (ProjectFileName, GlobalProperties) [TargetNames] jako seznam položek sestavení.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud zadaný cíl v `Targets` selže a `RunEachTargetSeparately` je `true`, úloha nadále sestavení zbývající cíle.  
  
 Pokud chcete vytvořit výchozí cíle, použijte [úlohy nástroje MSBuild](../msbuild/msbuild-task.md) a nastavte `Projects` rovna hodnotě parametru `$(MSBuildProjectFile)`.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad volání `TargetA` z uvnitř `CallOtherTargets`.  
  
```xml  
<Project DefaultTargets="CallOtherTargets"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <Target Name="CallOtherTargets">  
        <CallTarget Targets="TargetA"/>  
    </Target>  
  
    <Target Name="TargetA">  
        <Message Text="Building TargetA..." />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Cíle](../msbuild/msbuild-targets.md)