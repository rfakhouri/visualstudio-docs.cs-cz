---
title: 'Postupy: určení umístění, kde budou koncoví uživatelé instalovat z | Dokumentace Microsoftu'
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
- deploying applications [ClickOnce], specifying an installation URL
- URLs, specifying an installation URL
- installation, specifying installation an URL
- Installation URL property
ms.assetid: 04a804bf-ed55-4a7a-a1e6-f63ed99c0276
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 68f50fe847d1432292491cd2970c7897eb1388da
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683309"
---
# <a name="how-to-specify-the-location-where-end-users-will-install-from"></a>Postupy: Určení umístění, z něhož mohou instalovat koncoví uživatelé
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: určení umístění kde koncoví uživatelé budou instalovat z](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-the-location-where-end-users-will-install-from).  
  
Při publikování [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace, umístění, kde uživatelé ke stažení a instalaci aplikace není nutně umístění, kde nejprve publikovat aplikace. Například v některých organizacích může vývojář publikování aplikace na testovacím serveru a pak by správce přesunout aplikaci na webový server.  
  
 V takovém případě můžete použít `Installation URL` vlastnosti a určit tak webový server, kde budou moct uživatelé aplikaci stáhnout. To je nezbytné, aby manifest aplikace věděla, kam chcete vyhledat aktualizace.  
  
 `Installation URL` Vlastnost lze nastavit na **publikovat** stránku **Návrháře projektu**.  
  
 **Poznámka:** `Installation URL` vlastnost můžete nastavit také pomocí **PublishWizard**. Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-specify-an-installation-url"></a>Chcete zadat adresu URL instalace  
  
1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **publikovat** kartu.  
  
3.  Do pole Adresa URL instalace, zadejte umístění instalace pomocí plně kvalifikovanou adresu URL pomocí formátu http://www.microsoft.com/ApplicationName, nebo cestu UNC ve formátu \\\Server\ApplicationName.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: určení, kde sada Visual Studio zkopíruje soubory](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



