---
title: 'Postupy: Sestavování specifických cílů v řešení pomocí MSBuild.exe | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 53ce05490ac46d7a4f01010e5709364f5d35222d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977260"
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Postupy: Sestavování specifických cílů v řešení pomocí MSBuild.exe
Můžete použít *MSBuild.exe* k sestavování specifických cílů konkrétní projekty v řešení.

#### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>K sestavení specifické cílem určitého projektu v řešení

1. Na příkazovém řádku zadejte `MSBuild.exe <SolutionName>.sln`, kde `<SolutionName>` odpovídá názvu souboru řešení, která obsahuje cíl, který chcete spustit.

2. Zadejte cíl po `-target:` přepnout ve formátu \<ProjectName >:\<TargetName >. Pokud název projektu obsahuje některý ze znaků `%`, `$`, `@`, `;`, `.`, `(`, `)`, nebo `'`, nahraďte pomocí `_` v zadaném Název cíle.

## <a name="example"></a>Příklad
 Následující příklad provede `Rebuild` cíl `NotInSlnFolder` projektu a potom provede `Clean` cíl `InSolutionFolder` projekt, který se nachází v *NewFolder* složku řešení.

```cmd
msbuild SlnFolders.sln -target:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean
```

## <a name="troubleshooting"></a>Poradce při potížích

Pokud chcete zkontrolovat dostupné možnosti, můžete k tomu možnost ladění nástrojem MSBuild k dispozici. Nastavte proměnnou prostředí `MSBUILDEMITSOLUTION=1` a sestavte řešení. To vytvoří soubor MSBuild s názvem  *\<SolutionName >. sln.metaproj* , který se teď zobrazují v MSBuild interní řešení v okamžiku sestavení. Můžete si prohlédnout toto zobrazení můžete zjistit, jaké cíle jsou k dispozici pro sestavení.

Nejdou sestavit pomocí této proměnné prostředí, pokud je třeba interní zobrazení. Toto nastavení může způsobit problémy sestavení projektů v řešení.

## <a name="see-also"></a>Viz také:
- [Odkaz na příkazový řádek](../msbuild/msbuild-command-line-reference.md)
- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
- [MSBuild](../msbuild/msbuild.md)
- [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)
