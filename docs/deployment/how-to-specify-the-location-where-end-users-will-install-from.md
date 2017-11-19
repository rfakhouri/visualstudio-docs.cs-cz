---
title: "Postupy: určení umístění, kde budou koncoví uživatelé instalovat z | Microsoft Docs"
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
- deploying applications [ClickOnce], specifying an installation URL
- URLs, specifying an installation URL
- installation, specifying installation an URL
- Installation URL property
ms.assetid: 04a804bf-ed55-4a7a-a1e6-f63ed99c0276
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 41a601febff80b002512a3783d8405dc42e5d766
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-specify-the-location-where-end-users-will-install-from"></a>Postupy: Určení umístění, z něhož mohou instalovat koncoví uživatelé
Při publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, umístění, kde uživatelé ke stažení a instalaci aplikace není nutně umístění, kde jste původně publikovali aplikace. Například v některých organizacích může vývojář publikovat aplikaci na pracovní server a poté by správce přesuňte aplikace na webový server.  
  
 V takovém případě můžete použít `Installation URL` vlastnosti a určit tak webový server, kde budou uživatelé stáhnout aplikaci. To je nezbytné, aby manifest aplikace věděla, kde má být k dispozici aktualizace.  
  
 `Installation URL` Vlastnost lze nastavit u **publikovat** stránky **Návrhář projektu**.  
  
 **Poznámka:** `Installation URL` vlastnost lze nastavit také pomocí **PublishWizard**. Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-specify-an-installation-url"></a>Chcete zadat adresu URL instalace  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Do pole adresy URL instalace zadejte umístění instalace pomocí plně kvalifikovanou adresu URL pomocí formátu http://www.microsoft.com/ApplicationName nebo cestu UNC pomocí formátu \\\Server\ApplicationName.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Zadejte, kde zkopíruje soubory v sadě Visual Studio](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)