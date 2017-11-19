---
title: "Postupy: Zadejte ClickOnce do režimu Offline nebo Online režimu instalace | Microsoft Docs"
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
- ClickOnce deployment, specifying install mode
- install mode
- online applications
- offline applications
- ClickOnce install mode
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
caps.latest.revision: "8"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 5376ef32ce768100af8bc1c9f18267f7ac39895a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>Postupy: Určení offline nebo online režimu instalace ClickOnce
`Install Mode` Pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace určuje, zda aplikace bude k dispozici online nebo offline. Pokud vyberete **aplikace je k dispozici pouze online**, uživatel musí mít přístup k [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] publikování umístění (na webové stránce nebo sdílené složky) ke spuštění aplikace. Pokud vyberete **aplikace je k dispozici také offline**, aplikace přidá položky k **spustit** nabídky a **přidat nebo odebrat programy** dialogové okno; uživatel je možné aplikaci spustit, když nejsou připojeni.  
  
 `Install Mode` Lze nastavit u **publikovat** stránky **Návrhář projektu**.  
  
 **Poznámka:** `Install Mode` můžete také nastavit pomocí Průvodce publikování. Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>Chcete-li aplikaci ClickOnce k dispozici online pouze  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  V **režim instalace a nastavení** oblasti, klikněte **aplikace je k dispozici pouze online** tlačítko.  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>Chcete-li aplikaci ClickOnce k dispozici online nebo offline  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  V **režim instalace a nastavení** oblast, klikněte na tlačítko **aplikace je k dispozici také offline** tlačítko.  
  
     Při instalaci aplikace přidá položky k **spustit** nabídky a **přidat nebo odebrat programy** v Ovládacích panelech.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)