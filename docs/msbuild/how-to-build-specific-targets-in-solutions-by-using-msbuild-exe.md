---
title: 'Postupy: sestavování specifických cílů v řešení pomocí MSBuild.exe | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a8da11d510e5bed68def8e36a0f8104ae7350bfb
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36325398"
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Postupy: Sestavování specifických cílů v řešení pomocí nástroje MSBuild.exe
MSBuild.exe můžete sestavování specifických cílů konkrétní projekty v řešení.  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>K vytvoření konkrétní cíl konkrétní projektu v řešení  
  
1.  Na příkazovém řádku zadejte `MSBuild.exe <SolutionName>.sln`, kde `<SolutionName>` odpovídá názvu souboru, řešení, která obsahuje cíl, který chcete spustit.  
  
2. Zadejte cíl po `/target:` přepínač ve formátu **`ProjectName`** `:` **`TargetName`**. Pokud název projektu obsahuje znaky `%`, `$`, `@`, `;`, `.`, `(`, `)`, nebo `'`, nahraďte je `_` v zadané Název cílové.
  
## <a name="example"></a>Příklad  
 Následující příklad spustí `Rebuild` cíl `NotInSlnFolder` projektu a potom provede `Clean` cíl `InSolutionFolder` projektu, který je umístěný ve `NewFolder` složce řešení.  
  
```cmd
msbuild SlnFolders.sln /target:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean`
```

## <a name="troubleshooting"></a>Poradce při potížích

Pokud chcete zkontrolovat dostupné možnosti, můžete k tomu možnost ladění poskytované MSBuild. Nastavit proměnnou prostředí `MSBUILDEMITSOLUTION=1` a sestavte řešení. Vznikne tak MSBuild soubor s názvem `<SolutionName>.sln.metaproj` MSBuild na interní zobrazení řešení, zobrazuje v čase vytvoření buildu. Si můžete prohlédnout tohoto zobrazení a určit, jaké cíle jsou k dispozici pro sestavení.

Nevytvářejte pomocí této proměnné prostředí, nastavit, pokud je nutné toto interní zobrazení. Toto nastavení může způsobit problémy sestavení projektů ve vašem řešení.

## <a name="see-also"></a>Viz také  
 [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [ Nástroje MSBuild](../msbuild/msbuild.md)  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)
