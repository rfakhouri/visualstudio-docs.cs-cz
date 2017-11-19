---
title: "Createcsharpmanifestresourcename – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
caps.latest.revision: "8"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 9d18d7809357c8f4fa7bce796e7f05981a0f8c99
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName – úloha
Vytvoří [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]-manifestu název stylu z daného RESX název souboru nebo jiný prostředek.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry [createcsharpmanifestresourcename – úloha](../msbuild/createcsharpmanifestresourcename-task.md).  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem>`[]` výstupní parametr jen pro čtení.<br /><br /> Výsledný manifestu názvy.|  
|`ResourceFiles`|Požadované `String` parametr.<br /><br /> Název souboru prostředků, ze které chcete vytvořit [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] názvu manifestu.|  
|`RootNamespace`|Volitelné `String` parametr.<br /><br /> Kořenového oboru názvů souboru prostředků, obvykle převzat ze souboru projektu. Může být `null`.|  
|`PrependCultureAsDirectory`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, název jazykové verze je přidán jako název adresáře těsně před název prostředku manifestu. Výchozí hodnota je `true`.|  
|`ResourceFilesWithManifestResourceNames`|Volitelné jen pro čtení `String` výstupní parametr.<br /><br /> Vrátí název souboru prostředků, který teď zahrnuje název prostředku manifestu.|  
  
## <a name="remarks"></a>Poznámky  
 [Createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md) Určuje název odpovídající prostředku manifestu přiřazení k dané resx nebo jiný soubor prostředků. Úloha obsahuje logický název souboru prostředků a potom ji připojí k výstupní parametr jako metadata.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)