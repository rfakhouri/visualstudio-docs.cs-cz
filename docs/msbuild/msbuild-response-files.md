---
title: "Soubory odezvy nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7520a9f51f0d9420039728a75e84d4ed16583738
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-response-files"></a>Soubory odezvy nástroje MSBuild
Soubory odezvy (.rsp) jsou textové soubory, které obsahují MSBuild.exe spínačů příkazového řádku. Každý přepínač může být na samostatném řádku nebo může být všech přepínačů na jeden řádek. Řádky poznámky začínají  **#**  symbol. **@**  Přepínač se používá k předat MSBuild.exe jiný soubor odpovědi.  
  
 Soubor odpovědí je speciální .rsp soubor, který MSBuild.exe automaticky použije při sestavování projektu. Tento soubor MSBuild.rsp, musí být ve stejném adresáři jako MSBuild.exe, v opačném případě se nebude nalezen. Tento soubor k určení výchozí spínačů příkazového řádku k MSBuild.exe můžete upravit. Například pokud chcete použít stejné protokolovacího nástroje pokaždé, když vytváříte projekt, můžete přidat **/logger** přepněte do MSBuild.rsp a MSBuild.exe použije protokolovacího nástroje pokaždé, když je založený na projekt.  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)