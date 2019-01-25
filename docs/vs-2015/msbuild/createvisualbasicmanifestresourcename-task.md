---
title: Createvisualbasicmanifestresourcename – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateVisualBasicManifestResourceName task
- CreateVisualBasicManifestResourceName task [MSBuild]
ms.assetid: 251c47b9-de32-414b-a138-bf45290af12e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d49f47a935f82d1c03af9faad941470107e2eca6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54761653"
---
# <a name="createvisualbasicmanifestresourcename-task"></a>CreateVisualBasicManifestResourceName – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Vytvoří [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]– název manifestu stylu z názvu souboru .resx dané nebo jiný prostředek.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry [createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md).  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr jen pro čtení.<br /><br /> Výsledný manifestu názvy.|  
|`ResourceFiles`|Vyžaduje `String` parametru.<br /><br /> Název souboru prostředků, ze kterého se má vytvořit [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] název souboru manifestu.|  
|`RootNamespace`|Volitelné `String` parametru.<br /><br /> Kořenový obor názvů souboru prostředků, obvykle provedeny ze souboru projektu. Může být `null`.|  
|`PrependCultureAsDirectory`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, název jazykové verze se přidá jako název adresáře těsně před název prostředku manifestu. Výchozí hodnota je `true`.|  
|`ResourceFilesWithManifestResourceNames`|Volitelné jen pro čtení `String` výstupní parametr.<br /><br /> Vrátí název souboru prostředků, která nyní obsahuje název prostředku manifestu.|  
  
## <a name="remarks"></a>Poznámky  
 [Createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md) Určuje název odpovídající prostředku manifestu pro přiřazení k dané .resx nebo jiný soubor prostředku. Úloha obsahuje logický název souboru prostředků a připojí ho k výstupní parametr jako metadata.  
  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
