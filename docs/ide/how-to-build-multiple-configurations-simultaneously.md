---
title: 'Postupy: sestavení více konfigurací současně | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 552ca372b567ee568ac7f70a520e6e11a104afec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>Postupy: sestavení více konfigurací současně
Většina typů projekty s více, nebo i všechny jeho konfigurace sestavení ve stejnou dobu můžete vytvořit pomocí **dávkové sestavení** dialogové okno. Však nemůže vytvořit následující typy projektů v různých konfiguracích sestavení ve stejnou dobu:  
  
1.  [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace vytvořená pro systém Windows pomocí jazyka JavaScript.  
  
2.  Všechny projekty Visual Basic.  
  
 Další informace o konfiguracích sestavení najdete v tématu [Rady pro pochopení konfigurace sestavení](../ide/understanding-build-configurations.md).  
  
### <a name="to-build-a-project-in-multiple-build-configurations"></a>Pro vytvoření projektu v různých konfiguracích sestavení  
  
1.  Na řádku nabídek zvolte **sestavení** > **dávkové sestavení**.  
  
2.  V **sestavení** sloupce, zaškrtněte políčka u konfigurace, ve kterých chcete sestavení projektu.  
  
    > [!TIP]
    >  Chcete-li upravit nebo vytvořit konfigurace sestavení řešení, zvolte **sestavení** > **nástroje Configuration Manager** v řádku nabídek otevřete **nástroje Configuration Manager** Dialogové okno. Poté, co jste upravili konfigurace sestavení řešení, vyberte **znovu sestavit** tlačítka na **dávkové sestavení** dialogové okno Aktualizovat všechny konfigurace pro projekty v řešení sestavení.  
  
3.  Vyberte **sestavení** nebo **znovu sestavit** tlačítka pro sestavení projektu s konfigurací, které jste zadali.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)   
 [Pochopení konfigurace sestavení](../ide/understanding-build-configurations.md)   
 [Vytvářet více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)