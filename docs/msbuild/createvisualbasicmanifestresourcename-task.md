---
title: Createvisualbasicmanifestresourcename – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 948b27aa9e2b800929d9f507535aee1395d45344
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53871223"
---
# <a name="createvisualbasicmanifestresourcename-task"></a>CreateVisualBasicManifestResourceName – úloha
Vytvoří [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]-manifestu název stylu z danou *RESX* název souboru nebo jiného prostředku.  

## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry [createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md).  


| Parametr | Popis |
| - | - |
| `ManifestResourceNames` | <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr jen pro čtení.<br /><br /> Výsledný manifestu názvy. |
| `ResourceFiles` | Vyžaduje `String` parametru.<br /><br /> Název souboru prostředků, ze kterého se má vytvořit [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] název souboru manifestu. |
| `RootNamespace` | Volitelné `String` parametru.<br /><br /> Kořenový obor názvů souboru prostředků, obvykle provedeny ze souboru projektu. Může být `null`. |
| `PrependCultureAsDirectory` | Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, název jazykové verze se přidá jako název adresáře těsně před název prostředku manifestu. Výchozí hodnota je `true`. |
| `ResourceFilesWithManifestResourceNames` | Volitelné jen pro čtení `String` výstupní parametr.<br /><br /> Vrátí název souboru prostředků, která nyní obsahuje název prostředku manifestu. |

## <a name="remarks"></a>Poznámky  
 [Createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md) Určuje název odpovídající prostředku manifestu přiřadit daného *RESX* nebo jiný soubor prostředku. Úloha obsahuje logický název souboru prostředků a připojí ho k výstupní parametr jako metadata.  

 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  

## <a name="see-also"></a>Viz také:  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)