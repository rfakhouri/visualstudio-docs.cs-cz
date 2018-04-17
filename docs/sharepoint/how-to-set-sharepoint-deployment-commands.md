---
title: 'Postupy: nastavení příkazů nasazení služby SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8779ba4ee4cf9803982d9849b3af7c83930d8a5b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>Postupy: Nastavení příkazů nasazení služby SharePoint
  Proces nasazení můžete přizpůsobit nastavení příkazy před nasazením a po nasazení. Tyto příkazy spustit před a po dalších akcí nasazení při ladění řešení služby SharePoint v sadě Visual Studio.  
  
### <a name="to-add-a-pre-deployment-command"></a>Chcete-li přidat příkaz před nasazením  
  
1.  Na řádku nabídek zvolte **projektu**, * ProjectName ***vlastnosti**.  
  
2.  Vyberte **SharePoint** kartě.  
  
3.  V **před nasazením příkazového řádku** textové pole, zadejte MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.  
  
     Například pro zobrazení seznamu obsah adresáře, než bude dokončeno nasazení, zadejte **dir**.  
  
### <a name="to-add-a-post-deployment-command"></a>Chcete-li přidat příkaz po nasazení  
  
1.  Na řádku nabídek zvolte **projektu**, * ProjectName ***vlastnosti**.  
  
2.  Vyberte **SharePoint** kartě.  
  
3.  V **po nasazení příkazového řádku** text zadejte MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.  
  
     Po dokončení nasazení, zobrazit obsah adresáře, zadejte **dir**. Chcete-li proměnnou MSBuild zkopírujte sestavení z adresáře sestavení, zadejte **zkopírujte $(TargetPath) c:\DeploymentDirectory**.  
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  