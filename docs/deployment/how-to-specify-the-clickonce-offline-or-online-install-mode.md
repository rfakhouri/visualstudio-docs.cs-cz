---
title: 'Postupy: Určení ClickOnce v režimu Offline nebo Online režimu instalace | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ef19b966bb9d934975eebd00399b401e768922d1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55011673"
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>Postupy: Zadejte ClickOnce offline nebo online režimu instalace
`Install Mode` Pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace určuje, zda aplikace bude k dispozici online nebo offline. Pokud zvolíte **aplikace je dostupná pouze online**, uživatel musí mít přístup k [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] umístění (webové stránky nebo sdílené složky) Chcete-li spustit aplikaci pro publikování. Při výběru **aplikace je k dispozici také v režimu offline**, aplikace přidá položky do **Start** nabídky a **přidat nebo odebrat programy** dialogové okno; uživatel je možné aplikaci spustit, když nejsou připojeni.  
  
 `Install Mode` Lze nastavit na **publikovat** stránku **Návrháře projektu**.  
  
 **Poznámka:** `Install Mode` můžete také nastavit pomocí Průvodce publikováním. Další informace najdete v tématu [jak: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>Chcete-li aplikaci ClickOnce zpřístupnit online pouze  
  
1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **publikovat** kartu.  
  
3.  V **režim instalace a nastavení** oblast, klikněte na tlačítko **aplikace je dostupná pouze online** přepínač.  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>Chcete-li aplikaci ClickOnce zpřístupnit online nebo offline  
  
1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **publikovat** kartu.  
  
3.  V **režim instalace a nastavení** oblast, klikněte na tlačítko **aplikace je k dispozici také v režimu offline** přepínač.  
  
     Při instalaci aplikace přidá položky do **Start** nabídky a **přidat nebo odebrat programy** v Ovládacích panelech.  
  
## <a name="see-also"></a>Viz také:  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Volba strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)