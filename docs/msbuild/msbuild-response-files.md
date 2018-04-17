---
title: Soubory odezvy nástroje MSBuild | Microsoft Docs
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
- response files, MSBuild
- MSBuild, response files
- MSBuild, .rsp files
- .rsp files
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c619a21588ed2026e360e01be05af7012cf1304b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-response-files"></a>Soubory odezvy nástroje MSBuild
Soubory odezvy (.rsp) jsou textové soubory, které obsahují MSBuild.exe spínačů příkazového řádku. Každý přepínač může být na samostatném řádku nebo může být všech přepínačů na jeden řádek. Řádky poznámky začínají **#** symbol. **@** Přepínač se používá k předat MSBuild.exe jiný soubor odpovědi.  
  
## <a name="msbuildrsp"></a>MSBuild.rsp
Soubor odpovědí je speciální .rsp soubor, který MSBuild.exe automaticky použije při sestavování projektu. Tento soubor MSBuild.rsp, musí být ve stejném adresáři jako MSBuild.exe, v opačném případě se nebude nalezen. Tento soubor k určení výchozí spínačů příkazového řádku k MSBuild.exe můžete upravit. Například pokud chcete použít stejné protokolovacího nástroje pokaždé, když vytváříte projekt, můžete přidat **/logger** přepněte do MSBuild.rsp a MSBuild.exe použije protokolovacího nástroje pokaždé, když je založený na projekt.  

## <a name="directorybuildrsp"></a>Directory.Build.rsp
Ve verzi 15,6 operací a jeho novější verze nástroje MSBuild hledat nadřazeného adresáře projektu pro soubor s názvem `Directory.Build.rsp`.  To může být užitečné v úložiště zdrojového kódu a poskytovat výchozí argumenty během sestavení příkazového řádku.  Ho lze také zadat argumenty příkazového řádku hostované sestavení.

## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)