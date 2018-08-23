---
title: 'Postupy: sestavování specifických cílů v řešení pomocí MSBuild.exe | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bdc5d824d802916c38ef0267dae0de85e8814e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631585"
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Postupy: Sestavování specifických cílů v řešení pomocí nástroje MSBuild.exe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: vytváření specifických cílů v řešení podle pomocí MSBuild.exe](https://docs.microsoft.com/visualstudio/msbuild/how-to-build-specific-targets-in-solutions-by-using-msbuild-exe).  
  
  
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
 [ Nástroj MSBuild](msbuild.md)  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)


