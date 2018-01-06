---
title: "Soubory odezvy nástroje MSBuild | Microsoft Docs"
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
- response files, MSBuild
- MSBuild, response files
- MSBuild, .rsp files
- .rsp files
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
caps.latest.revision: "3"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d2d204535d24fc1ef000c897f45bdb51710dfee9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-response-files"></a>Soubory odezvy nástroje MSBuild
Soubory odezvy (.rsp) jsou textové soubory, které obsahují MSBuild.exe spínačů příkazového řádku. Každý přepínač může být na samostatném řádku nebo může být všech přepínačů na jeden řádek. Řádky poznámky začínají  **#**  symbol.  **@**  Přepínač se používá k předat MSBuild.exe jiný soubor odpovědi.  
  
 Soubor odpovědí je speciální .rsp soubor, který MSBuild.exe automaticky použije při sestavování projektu. Tento soubor MSBuild.rsp, musí být ve stejném adresáři jako MSBuild.exe, v opačném případě se nebude nalezen. Tento soubor k určení výchozí spínačů příkazového řádku k MSBuild.exe můžete upravit. Například pokud chcete použít stejné protokolovacího nástroje pokaždé, když vytváříte projekt, můžete přidat **/logger** přepněte do MSBuild.rsp a MSBuild.exe použije protokolovacího nástroje pokaždé, když je založený na projekt.  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)