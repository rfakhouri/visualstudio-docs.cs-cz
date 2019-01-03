---
title: Soubory odezvy nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: 33156a0614ad47839187056e4e0a24b5ee2f7ae2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53989669"
---
# <a name="msbuild-response-files"></a>Soubory odezvy nástroje MSBuild
Odpověď (*.rsp*) soubory jsou textové soubory, které obsahují *MSBuild.exe* přepínače příkazového řádku. Každý přepínač může být na samostatném řádku nebo všechny přepínače může být na jednom řádku. Komentář řádky jsou uvedena **#** symbol. **@** Přepínač slouží k předání jiný soubor odezvy *MSBuild.exe*.  
  
## <a name="msbuildrsp"></a>MSBuild.rsp
Soubor nástroj je speciální *.rsp* souboru, který *MSBuild.exe* automaticky používá při sestavování projektu. Tento soubor *MSBuild.rsp*, musí být ve stejném adresáři jako *MSBuild.exe*, jinak nebude nalezena. Můžete upravit tento soubor k určení výchozího přepínače příkazového řádku k *MSBuild.exe*. Například, pokud používáte stejný protokolovač pokaždé, když se sestavení projektu, můžete přidat **-protokolovací nástroj** přepnout na *MSBuild.rsp*, a *MSBuild.exe* bude použijte protokolovací nástroj pokaždé, když se Projekt se vytvořil. 

## <a name="directorybuildrsp"></a>Directory.Build.rsp
Ve verzi 15.6 a vyšší než MSBuild vyhledá nadřazené adresáře projektu pro soubor s názvem *Directory.Build.rsp*.  To může být užitečné v úložiště zdrojového kódu během sestavení příkazového řádku poskytovat výchozí argumenty.  To také umožňuje zadat argumenty příkazového řádku hostovaných buildů. 

## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Odkaz na příkazový řádek](../msbuild/msbuild-command-line-reference.md)