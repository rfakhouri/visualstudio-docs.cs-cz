---
title: Createcsharpmanifestresourcename – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b7ddede6870a982520b87cf8ec497788b4731244
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640542"
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName – úloha
Vytvoří [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]-manifestu název stylu z danou *RESX* název souboru nebo jiného prostředku.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry [createcsharpmanifestresourcename – úloha](../msbuild/createcsharpmanifestresourcename-task.md).


| Parametr | Popis |
| - | - |
| `ManifestResourceNames` | <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr jen pro čtení.<br /><br /> Výsledný manifestu názvy. |
| `ResourceFiles` | Vyžaduje `String` parametru.<br /><br /> Název souboru prostředků, ze kterého se má vytvořit [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] název souboru manifestu. |
| `RootNamespace` | Volitelné `String` parametru.<br /><br /> Kořenový obor názvů souboru prostředků, obvykle provedeny ze souboru projektu. Může být `null`. |
| `PrependCultureAsDirectory` | Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, název jazykové verze se přidá jako název adresáře těsně před název prostředku manifestu. Výchozí hodnota je `true`. |
| `ResourceFilesWithManifestResourceNames` | Volitelné jen pro čtení `String` výstupní parametr.<br /><br /> Vrátí název souboru prostředků, která nyní obsahuje název prostředku manifestu. |

## <a name="remarks"></a>Poznámky
 [Createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md) Určuje název odpovídající prostředku manifestu přiřadit daného *RESX* nebo jiný soubor prostředku. Úloha obsahuje logický název souboru prostředků a připojí ho k výstupní parametr jako metadata.

 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)