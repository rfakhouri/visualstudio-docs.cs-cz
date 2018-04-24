---
title: Soubory odezvy nástroje MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f685364bbcf69b8d4b91635cb42079f3f06e5311
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
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