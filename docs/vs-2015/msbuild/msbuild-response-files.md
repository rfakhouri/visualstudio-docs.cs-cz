---
title: Soubory odezvy nástroje MSBuild | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71fdc29db3e2af66c85637648bb0703e7f7d80c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633578"
---
# <a name="msbuild-response-files"></a>Soubory odezvy nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [soubory odezvy nástroje MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-response-files).  
  
  
Soubory odpovědí (.rsp) jsou textové soubory, které obsahují MSBuild.exe přepínače příkazového řádku. Každý přepínač může být na samostatném řádku nebo všechny přepínače může být na jednom řádku. Komentář řádky jsou uvedena **#** symbol. **@** Přepínač slouží k předání jiný soubor s odpovědí MSBuild.exe.  
  
 Soubor odpovědí automaticky je speciální .rsp soubor, který automaticky použije MSBuild.exe při sestavování projektu. Tento soubor MSBuild.rsp, musí být ve stejném adresáři jako MSBuild.exe, jinak, nebude nalezen. Můžete upravit tento soubor k určení výchozího přepínače příkazového řádku MSBuild.exe. Například pokud používáte stejný protokolovač pokaždé, když se sestavení projektu, můžete přidat **/logger** přepnout na MSBuild.rsp a MSBuild.exe použije protokolovač pokaždé, když je sestaven projekt.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)



