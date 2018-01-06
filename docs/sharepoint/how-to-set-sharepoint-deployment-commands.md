---
title: "Postupy: nastavení příkazů nasazení služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, deploying
ms.assetid: 289c8c33-a603-434e-889f-a0d0a1736ecb
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d5692195f340ce347df0bc6f8ad2d60225f24e6d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>Postupy: Nastavení příkazů nasazení služby SharePoint
  Proces nasazení můžete přizpůsobit nastavení příkazy před nasazením a po nasazení. Tyto příkazy spustit před a po dalších akcí nasazení při ladění řešení služby SharePoint v sadě Visual Studio.  
  
### <a name="to-add-a-pre-deployment-command"></a>Chcete-li přidat příkaz před nasazením  
  
1.  Na řádku nabídek zvolte **projektu**, *ProjectName***vlastnosti**.  
  
2.  Vyberte **SharePoint** kartě.  
  
3.  V **před nasazením příkazového řádku** textové pole, zadejte MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.  
  
     Například pro zobrazení seznamu obsah adresáře, než bude dokončeno nasazení, zadejte **dir**.  
  
### <a name="to-add-a-post-deployment-command"></a>Chcete-li přidat příkaz po nasazení  
  
1.  Na řádku nabídek zvolte **projektu**, *ProjectName***vlastnosti**.  
  
2.  Vyberte **SharePoint** kartě.  
  
3.  V **po nasazení příkazového řádku** text zadejte MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.  
  
     Po dokončení nasazení, zobrazit obsah adresáře, zadejte **dir**. Chcete-li proměnnou MSBuild zkopírujte sestavení z adresáře sestavení, zadejte **zkopírujte $(TargetPath) c:\DeploymentDirectory**.  
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  