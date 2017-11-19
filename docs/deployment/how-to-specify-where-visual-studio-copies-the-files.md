---
title: "Postupy: Zadejte, kde zkopíruje soubory v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, specifying location
- Publish Location property
ms.assetid: 6c552700-dda3-49fe-af98-4717344fda07
caps.latest.revision: "12"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 0e1bfe41d34c1c507818f7bb255425d31dc2f343
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-specify-where-visual-studio-copies-the-files"></a>Postupy: Určení cíle kopírování souborů sadou Visual Studio
Když publikujete aplikaci s použitím technologie ClickOnce, `Publish Location` vlastnost určuje umístění, kam jsou umístěny soubory aplikace a manifest. Může se jednat o cestu k souboru nebo cestu k serveru FTP.  
  
 Můžete zadat `Publish Location` vlastnost **publikovat** stránky **Návrhář projektu**, nebo pomocí Průvodce publikování. Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
> [!NOTE]
>  Při instalaci více než jedna verze aplikace s použitím technologie ClickOnce, instalaci starší verze aplikace přesune do složky s názvem Archiv v umístění pro publikování, který určíte. Archivace dřívější verze tímto způsobem udržuje instalační adresář vymazat složek ze starší verze.  
  
### <a name="to-specify-a-publishing-location"></a>Chcete-li určit umístění pro publikování  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  V **publikování umístění** pole, zadejte umístění pro publikování pomocí jedné z následujících formátů:  
  
    -   Chcete-li publikovat na sdílenou složku nebo disk cestu k souboru, zadejte cestu k pomocí cesty UNC (\\\Server\ApplicationName) nebo cesta k souboru (C:\Deploy\ApplicationName).  
  
    -   Pokud chcete publikovat na FTP server, zadejte cestu k pomocí formátu ftp://ftp.microsoft.com/ApplicationName.  
  
     Všimněte si, že text musí být součástí **umístění pro publikování** pole v pořadí pro Procházet (**...** ) tlačítko pracovat.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)