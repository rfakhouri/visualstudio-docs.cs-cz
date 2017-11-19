---
title: "Writelinestofile – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#WriteLinesToFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- WriteLinesToFile task [MSBuild]
- MSBuild, WriteLinesToFile task
ms.assetid: 9c8862ac-8da5-4437-9430-ecc30421f1c9
caps.latest.revision: "9"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 60b84cf967e92c1669cae9fbbcdabcc4e5acb159
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="writelinestofile-task"></a>WriteLinesToFile – úloha
Zapíše cesty zadaných položek pro zadaný textový soubor.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `WriteLinestoFile` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`File`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje soubor k zápisu položky, které chcete.|  
|`Lines`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje položky, které chcete zapisovat do souboru.|  
|`Overwrite`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, úloha přepíše existující obsah v souboru.|  
|`Encoding`|Volitelné `String` parametr.<br /><br /> Vybere kódování, například "Unicode" znaků.  Viz také <xref:System.Text.Encoding>.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud `Overwrite` je `true`, vytvoří nový soubor, zapisovat obsah do souboru a poté uzavře soubor. Jestliže cílový soubor již existuje, je přepsán. Pokud `Overwrite` je `false`, připojí obsah do souboru, vytváření cílový soubor, pokud ještě neexistuje.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `WriteLinesToFile` úloh zápis cesty položky v `MyItems` kolekce do souboru určeného položek `MyTextFile` kolekce položek.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyTextFile Include="Items.txt"/>  
        <MyItems Include="*.cs"/>  
    </ItemGroup>  
  
    <Target Name="WriteToFile">  
        <WriteLinesToFile  
            File="@(MyTextFile)"  
            Lines="@(MyItems)"  
            Overwrite="true"  
            Encoding="Unicode"/>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)