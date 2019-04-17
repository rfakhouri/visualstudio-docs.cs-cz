---
title: Soubory odezvy nástroje MSBuild | Dokumentace Microsoftu
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
- response files, MSBuild
- MSBuild, response files
- MSBuild, .rsp files
- .rsp files
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a1ce11edac37368b9c4993a87a8c2b3e734b7862
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59649612"
---
# <a name="msbuild-response-files"></a>Soubory odezvy nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Soubory odpovědí (.rsp) jsou textové soubory, které obsahují MSBuild.exe přepínače příkazového řádku. Každý přepínač může být na samostatném řádku nebo všechny přepínače může být na jednom řádku. Komentář řádky jsou uvedena **#** symbol. **@** Přepínač slouží k předání jiný soubor s odpovědí MSBuild.exe.  
  
 Soubor odpovědí automaticky je speciální .rsp soubor, který automaticky použije MSBuild.exe při sestavování projektu. Tento soubor MSBuild.rsp, musí být ve stejném adresáři jako MSBuild.exe, jinak, nebude nalezen. Můžete upravit tento soubor k určení výchozího přepínače příkazového řádku MSBuild.exe. Například pokud používáte stejný protokolovač pokaždé, když se sestavení projektu, můžete přidat **/logger** přepnout na MSBuild.rsp a MSBuild.exe použije protokolovač pokaždé, když je sestaven projekt.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)
