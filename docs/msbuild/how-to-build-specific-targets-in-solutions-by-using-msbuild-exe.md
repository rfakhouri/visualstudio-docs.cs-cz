---
title: "Postupy: sestavování specifických cílů v řešení pomocí MSBuild.exe | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 66ec27d619b64353bf0cbac6a8b92c582ef5a590
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Postupy: Sestavování specifických cílů v řešení pomocí nástroje MSBuild.exe
MSBuild.exe můžete sestavování specifických cílů konkrétní projekty v řešení.  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>K vytvoření konkrétní cíl konkrétní projektu v řešení  
  
1.  Na příkazovém řádku zadejte `MSBuild.exe <SolutionName>.sln`, kde `<SolutionName>` odpovídá názvu souboru, řešení, která obsahuje cíl, který chcete spustit.  
  
2.  Zadejte cíl po **/t** přepínač ve formátu *ProjectName*:*TargetName*.  
  
## <a name="example"></a>Příklad  
 Následující příklad spustí `Rebuild` cíl `NotInSlnFolder` projektu a potom provede `Clean` cíl `InSolutionFolder` projektu, který je umístěný ve `NewFolder` složce řešení.  
  
```  
msbuild SlnFolders.sln /t:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean  
```  
  
## <a name="see-also"></a>Viz také  
 [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Nástroje MSBuild](../msbuild/msbuild.md)  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)