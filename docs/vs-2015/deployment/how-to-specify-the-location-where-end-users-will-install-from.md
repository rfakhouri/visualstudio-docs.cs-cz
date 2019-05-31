---
title: 'Postupy: Zadejte umístění, kde budou koncoví uživatelé instalovat z | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
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
manager: jillfra
ms.openlocfilehash: 3139cb337428dfc0c14e5bae47e682ce169bc81d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60108500"
---
# <a name="how-to-specify-the-location-where-end-users-will-install-from"></a>Postupy: Určení umístění, z něhož budou instalovat koncoví uživatelé
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při publikování [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace, umístění, kde uživatelé ke stažení a instalaci aplikace není nutně umístění, kde nejprve publikovat aplikace. Například v některých organizacích může vývojář publikování aplikace na testovacím serveru a pak by správce přesunout aplikaci na webový server.  
  
 V takovém případě můžete použít `Installation URL` vlastnosti a určit tak webový server, kde budou moct uživatelé aplikaci stáhnout. To je nezbytné, aby manifest aplikace věděla, kam chcete vyhledat aktualizace.  
  
 `Installation URL` Vlastnost lze nastavit na **publikovat** stránku **Návrháře projektu**.  
  
 **Poznámka:** `Installation URL` vlastnost můžete nastavit také pomocí **PublishWizard**. Další informace najdete v tématu [jak: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-specify-an-installation-url"></a>Chcete zadat adresu URL instalace  
  
1. S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2. Klikněte na tlačítko **publikovat** kartu.  
  
3. Do pole Adresa URL instalace, zadejte umístění instalace pomocí plně kvalifikovanou adresu URL pomocí formátu http://www.microsoft.com/ApplicationName, nebo cestu UNC ve formátu \\\Server\ApplicationName.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Zadejte, kde sada Visual Studio zkopíruje soubory](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
