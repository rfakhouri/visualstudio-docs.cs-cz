---
title: 'Postupy: Zadejte, kam soubory kopie sady Visual Studio 2015 | Dokumentace Microsoftu'
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
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
manager: jillfra
ms.openlocfilehash: 8759145dd4a7647cad6e9964ae1f1c97d333b626
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65226158"
---
# <a name="how-to-specify-where-visual-studio-copies-the-files"></a>Postupy: Určení cíle kopírování souborů sadou Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Když publikujete aplikaci s použitím technologie ClickOnce, `Publish Location` vlastnost určuje umístění, kde jsou umístěny soubory aplikace a manifest. Může jít cestu k souboru nebo cesta k serveru FTP.

 Můžete zadat `Publish Location` vlastnost **publikovat** stránku **Návrháře projektu**, nebo pomocí Průvodce publikováním. Další informace najdete v tématu [jak: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).

> [!NOTE]
> Při instalaci více než jednu verzi aplikace s použitím technologie ClickOnce, instalace přesune starší verze této aplikace do složky s názvem Archiv v umístění pro publikování, který zadáte. Archivace dřívějších verzí tímto způsobem udržuje instalační adresář čistý od složek starší verze.

### <a name="to-specify-a-publishing-location"></a>Chcete-li určit umístění pro publikování

1. S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.

2. Klikněte na tlačítko **publikovat** kartu.

3. V **umístění publikování** zadejte umístění pro publikování pomocí jedné z následujících formátů:

   - Chcete-li publikovat do sdílené složky nebo disk cestu k souboru, zadejte cestu pomocí cesty UNC (\\\Server\ApplicationName) nebo cestu k souboru (C:\Deploy\ApplicationName).

   - Publikovat na FTP server, zadejte cestu pomocí formátu ftp:\//ftp.microsoft.com/ApplicationName.

     Všimněte si, že text musí být součástí **umístění pro publikování** pole mohl procházet (**...** ) tlačítko pro práci.

## <a name="see-also"></a>Viz také
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md) [jak: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
