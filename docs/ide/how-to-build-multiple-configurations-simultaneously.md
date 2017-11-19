---
title: "Postupy: sestavení více konfigurací současně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: eca23f38a27ac43246fd6fbf0b4449630ef3f64d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>Postupy: Sestavení více konfigurací současně
Většina typů projekty s více, nebo i všechny jeho konfigurace sestavení ve stejnou dobu můžete vytvořit pomocí **dávkové sestavení** dialogové okno. Však nemůže vytvořit následující typy projektů v různých konfiguracích sestavení ve stejnou dobu:  
  
1.  [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]aplikace vytvořená pro systém Windows pomocí jazyka JavaScript.  
  
2.  Všechny projekty Visual Basic.  
  
 Další informace o konfiguracích sestavení najdete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
### <a name="to-build-a-project-in-multiple-build-configurations"></a>Pro vytvoření projektu v různých konfiguracích sestavení  
  
1.  Na řádku nabídek zvolte **sestavení**, **dávkové sestavení**.  
  
2.  V **sestavení** sloupce, zaškrtněte políčka u konfigurace, ve kterých chcete sestavení projektu.  
  
    > [!TIP]
    >  Upravit nebo vytvořit konfigurace sestavení řešení, zvolte **sestavení**, **nástroje Configuration Manager** v řádku nabídek otevřete **nástroje Configuration Manager** dialogové okno. Poté, co jste upravili konfigurace sestavení řešení, vyberte **znovu sestavit** tlačítka na **dávkové sestavení** dialogové okno Aktualizovat všechny konfigurace pro projekty v řešení sestavení.  
  
3.  Vyberte **sestavení** nebo **znovu sestavit** tlačítka pro sestavení projektu s konfigurací, které jste zadali.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)   
 [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
 [Sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)