---
title: Zadejte, kam chcete zkopírovat soubory | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, specifying location
- Publish Location property
ms.assetid: 6c552700-dda3-49fe-af98-4717344fda07
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec54a2d3150b0e8e11b19d2ca739324d7388f1f0
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63407657"
---
# <a name="how-to-specify-where-visual-studio-copies-the-files"></a>Postupy: Zadejte, kde sada Visual Studio zkopíruje soubory
Když publikujete aplikaci s použitím technologie ClickOnce, `Publish Location` vlastnost určuje umístění, kde jsou umístěny soubory aplikace a manifest. Může jít cestu k souboru nebo cesta k serveru FTP.

 Můžete zadat `Publish Location` vlastnost **publikovat** stránku **Návrháře projektu**, nebo pomocí Průvodce publikováním. Další informace najdete v tématu [jak: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).

> [!NOTE]
> Při instalaci více než jednu verzi aplikace s použitím technologie ClickOnce, instalace přesune starší verze této aplikace do složky s názvem Archiv v umístění pro publikování, který zadáte. Archivace dřívějších verzí tímto způsobem udržuje instalační adresář čistý od složek starší verze.

### <a name="to-specify-a-publishing-location"></a>Chcete-li určit umístění pro publikování

1. S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.

2. Klikněte na tlačítko **publikovat** kartu.

3. V **umístění publikování** zadejte umístění pro publikování pomocí jedné z následujících formátů:

   - Chcete-li publikovat do sdílené složky nebo disk cestu k souboru, zadejte cestu pomocí cesty UNC (*\\\Server\ApplicationName*) nebo cestu k souboru (*C:\Deploy\ApplicationName*).

   - Chcete-li publikovat na FTP server, zadejte cestu ve formátu <em>ftp://ftp.microsoft.com/\<ApplicationName ></em>.

     Všimněte si, že text musí být součástí **umístění pro publikování** pole mohl procházet (**...** ) tlačítko pro práci.

## <a name="see-also"></a>Viz také:
- [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Postupy: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)