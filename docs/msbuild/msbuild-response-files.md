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
ms.openlocfilehash: a9ceab64ec0009dd143f42e1b94538690780f1bb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-response-files"></a>Soubory odezvy nástroje MSBuild
Soubory odezvy (.rsp) jsou textové soubory, které obsahují MSBuild.exe spínačů příkazového řádku. Každý přepínač může být na samostatném řádku nebo může být všech přepínačů na jeden řádek. Řádky poznámky začínají  **#**  symbol. **@**  Přepínač se používá k předat MSBuild.exe jiný soubor odpovědi.  
  
 Soubor odpovědí je speciální .rsp soubor, který MSBuild.exe automaticky použije při sestavování projektu. Tento soubor MSBuild.rsp, musí být ve stejném adresáři jako MSBuild.exe, v opačném případě se nebude nalezen. Tento soubor k určení výchozí spínačů příkazového řádku k MSBuild.exe můžete upravit. Například pokud chcete použít stejné protokolovacího nástroje pokaždé, když vytváříte projekt, můžete přidat **/logger** přepněte do MSBuild.rsp a MSBuild.exe použije protokolovacího nástroje pokaždé, když je založený na projekt.  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)