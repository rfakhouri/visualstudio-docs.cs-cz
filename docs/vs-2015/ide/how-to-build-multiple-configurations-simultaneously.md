---
title: 'Postupy: sestavení více konfigurací současně | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bca6142edff2eea293db50f0af9b8f86a4fc47dd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628250"
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>Postupy: Sestavení více konfigurací současně
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: sestavení více konfigurací současně](https://docs.microsoft.com/visualstudio/ide/how-to-build-multiple-configurations-simultaneously).  
  
Většina typů projektů s několika, nebo dokonce i všechny jejich konfigurace sestavení ve stejnou dobu můžete vytvářet pomocí **dávkové sestavení** dialogové okno. Však nemůže vytvořit následující typy projektů v několika konfiguracích sestavení ve stejnou dobu:  
  
1.  [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikace vytvořené pro Windows pomocí jazyka JavaScript.  
  
2.  Všechny projekty jazyka Visual Basic.  
  
 Další informace o konfiguracích sestavení naleznete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
### <a name="to-build-a-project-in-multiple-build-configurations"></a>Sestavení projektu v několika konfiguracích sestavení  
  
1.  V panelu nabídky zvolte **sestavení**, **dávkové sestavení**.  
  
2.  V **sestavení** sloupce, vyberte zaškrtávací políčka pro konfigurace, ve kterých chcete sestavit projekt.  
  
    > [!TIP]
    >  Chcete-li upravit nebo vytvořit vlastní proces sestavení pro řešení, zvolte **sestavení**, **nástroje Configuration Manager** na řádku nabídek otevřete **nástroje Configuration Manager** dialogové okno. Po úpravě konfigurace sestavení řešení, zvolte **znovu sestavit** tlačítko **dávkové sestavení** dialogové okno s aktualizací všech sestavení konfigurací pro projekty v řešení.  
  
3.  Zvolte **sestavení** nebo **znovu sestavit** tlačítka pro vytvoření projektu s konfiguracemi, které jste zadali.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)   
 [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
 [Sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)



