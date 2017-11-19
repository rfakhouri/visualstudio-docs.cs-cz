---
title: "CreateProperty – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
caps.latest.revision: "11"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a585c0c3065d16000737ebfd5c42e3f020c0074a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="createproperty-task"></a>CreateProperty – úloha
Naplní vlastnosti s předané hodnoty. To umožňuje hodnoty zkopírovány z jednu vlastnost nebo řetězec na jiný.  
  
## <a name="attributes"></a>Atributy  
 Následující tabulka popisuje parametry `CreateProperty` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Value`|Volitelné `String` výstupní parametr.<br /><br /> Určuje hodnotu, zkopírujte do nové vlastnosti.|  
|`ValueSetByTask`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje stejnou hodnotu jako `Value` parametr. Tento parametr použijte pouze v případě, že chcete vyhnout se nutnosti výstup vlastnost, která nastavuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] při vynechává nadřazených cíl protože výstupy jsou aktuální.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `CreateProperty` úlohy se má vytvořit `NewFile` vlastnost pomocí kombinace hodnot `SourceFilename` a `SourceFileExtension` vlastnost.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <SourceFilename>Module1</SourceFilename>  
        <SourceFileExtension>vb</SourceFileExtension>  
    </PropertyGroup>  
  
    <Target Name="CreateProperties">  
  
        <CreateProperty  
            Value="$(SourceFilename).$(SourceFileExtension)">  
            <Output  
                TaskParameter="Value"  
                PropertyName="NewFile" />  
        </CreateProperty>  
  
    </Target>  
  
</Project>  
```  
  
 Po spuštění projektu, hodnota `NewFile` vlastnost je `Module1.vb`.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)