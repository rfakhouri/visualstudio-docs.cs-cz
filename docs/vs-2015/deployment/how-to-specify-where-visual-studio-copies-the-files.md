---
title: 'Postupy: určení, kde sada Visual Studio zkopíruje soubory | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, specifying location
- Publish Location property
ms.assetid: 6c552700-dda3-49fe-af98-4717344fda07
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 52f19317bbfad963dd5bc4dc3e540640f9234c12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671950"
---
# <a name="how-to-specify-where-visual-studio-copies-the-files"></a>Postupy: Určení cíle kopírování souborů sadou Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: určení, kde sada Visual Studio zkopíruje soubory](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-where-visual-studio-copies-the-files).  
  
Když publikujete aplikaci s použitím technologie ClickOnce, `Publish Location` vlastnost určuje umístění, kde jsou umístěny soubory aplikace a manifest. Může jít cestu k souboru nebo cesta k serveru FTP.  
  
 Můžete zadat `Publish Location` vlastnost **publikovat** stránku **Návrháře projektu**, nebo pomocí Průvodce publikováním. Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
> [!NOTE]
>  Při instalaci více než jednu verzi aplikace s použitím technologie ClickOnce, instalace přesune starší verze této aplikace do složky s názvem Archiv v umístění pro publikování, který zadáte. Archivace dřívějších verzí tímto způsobem udržuje instalační adresář čistý od složek starší verze.  
  
### <a name="to-specify-a-publishing-location"></a>Chcete-li určit umístění pro publikování  
  
1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **publikovat** kartu.  
  
3.  V **umístění publikování** zadejte umístění pro publikování pomocí jedné z následujících formátů:  
  
    -   Chcete-li publikovat do sdílené složky nebo disk cestu k souboru, zadejte cestu pomocí cesty UNC (\\\Server\ApplicationName) nebo cestu k souboru (C:\Deploy\ApplicationName).  
  
    -   Chcete-li publikovat na FTP server, zadejte cestu k pomocí formátu ftp://ftp.microsoft.com/ApplicationName.  
  
     Všimněte si, že text musí být součástí **umístění pro publikování** pole mohl procházet (**...** ) tlačítko pro práci.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



