---
title: 'Postupy: Sestavování specifických cílů v řešení pomocí MSBuild.exe | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d07c0e11d47e20f43f4d4173de4bcc3c24b864b1
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59652721"
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Postupy: Sestavování určitých cílů do řešení nástrojem MSBuild.exe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

MSBuild.exe můžete použít k sestavování specifických cílů konkrétní projekty v řešení.  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>K sestavení specifické cílem určitého projektu v řešení  
  
1.  Na příkazovém řádku zadejte `MSBuild.exe <SolutionName>.sln`, kde `<SolutionName>` odpovídá názvu souboru řešení, která obsahuje cíl, který chcete spustit.  
  
2.  Zadejte cíl po **/t** přepnout ve formátu *ProjectName*:*TargetName*.  
  
## <a name="example"></a>Příklad  
 Následující příklad provede `Rebuild` cíl `NotInSlnFolder` projektu a potom provede `Clean` cíl `InSolutionFolder` projekt, který se nachází v `NewFolder` složku řešení.  
  
```  
msbuild SlnFolders.sln /t:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na příkazový řádek](../msbuild/msbuild-command-line-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [MSBuild](msbuild.md)  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)
