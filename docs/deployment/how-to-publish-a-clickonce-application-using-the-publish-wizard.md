---
title: "Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním | Microsoft Docs"
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
- ClickOnce deployment, publishing
- deploying applications [ClickOnce], Publish wizard
- Windows applications, ClickOnce deployments
- publishing, ClickOnce
ms.assetid: 2e4aa67c-4445-4f7b-9e03-9acb95829127
caps.latest.revision: "25"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: d314763f8ff4dc170148cca166e3ecdff051ae24
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-publish-a-clickonce-application-using-the-publish-wizard"></a>Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním
Pro aplikaci ClickOnce zpřístupnit uživatelům, je nutné ji publikovat na sdílené složky nebo cestu, FTP server nebo vyměnitelná média. Můžete publikovat aplikace pomocí Průvodce publikováním; je k dispozici v dalších vlastností souvisejících s publikováním **publikovat** stránky **Návrhář projektu**. Další informace najdete v tématu [publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md).  
  
 Před spuštěním Průvodce publikování, byste měli nastavit vlastnosti publikování správně. Například pokud chcete určit klíč k podepsání aplikace ClickOnce, můžete provést tak dále **podpisování** stránky **Návrhář projektu**. Další informace najdete v tématu [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md).  
  
> [!NOTE]
>  Při instalaci více než jedna verze aplikace s použitím technologie ClickOnce, instalaci starší verze aplikace přesune do složky s názvem Archiv v umístění pro publikování, který určíte. Archivace dřívější verze tímto způsobem udržuje instalační adresář vymazat složek ze starší verze.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě, v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, klikněte na tlačítko **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-publish-to-a-file-share-or-path"></a>K publikování do sdílené složky nebo cesta  
  
1.  V **Průzkumníku**, vyberte projekt aplikace.  
  
2.  Na **sestavení** nabídky, klikněte na tlačítko **publikovat**`Projectname`.  
  
     Zobrazí se v Průvodci publikováním.  
  
3.  V **kde chcete publikovat aplikaci?** stránky, zadejte platnou adresu serveru FTP nebo platnou cestu k souboru pomocí jednoho z formátů vidět a pak klikněte na tlačítko **Další**.  
  
4.  V **jak budou uživatelé aplikaci instalovat?** vyberte umístění, kde budou uživatelé k instalaci aplikace:  
  
    -   Pokud uživatelé nainstalují z webového serveru, klikněte na tlačítko **z webu** a zadejte adresu URL, která odpovídá cestu souboru zadanou v předchozím kroku. Klikněte na tlačítko **Další**. (Tato možnost se obvykle používá při zadání adresy FTP jako umístění pro publikování. Nepodporuje přímé stažení ze serveru FTP. Proto je nutné zadat adresu URL sem.)  
  
    -   Pokud uživatelé nainstalují aplikace přímo ze sdílené složky, klikněte na tlačítko **ze sdílené složky UNC cestu nebo sdílené složky**a potom klikněte na **Další**. (Toto je pro umístění formuláře c:\deploy\myapp publikování nebo \\\server\myapp.)  
  
    -   Pokud uživatelé nainstalují z vyměnitelného média, klikněte na tlačítko **z disku CD nebo DVD-ROM**a potom klikněte na **Další**.  
  
5.  Na **bude aplikace k dispozici do offline režimu?** klikněte na příslušnou možnost:  
  
    -   Pokud chcete povolit aplikaci spustit, když uživatel je odpojen od sítě, klikněte na tlačítko **Ano, tato aplikace bude k dispozici online nebo offline**. Zástupce na **spustit** nabídky se vytvoří pro danou aplikaci.  
  
    -   Pokud chcete aplikaci spustit přímo z umístění pro publikování, klikněte na tlačítko **Ne, tato aplikace je k dispozici pouze online**. Zástupce na **spustit** nabídky se nevytvoří.  
  
     Klikněte na tlačítko **Další** pokračujte.  
  
6.  Klikněte na tlačítko **Dokončit** k publikování aplikace.  
  
     Stav publikování se zobrazí v oznamovací oblasti stav.  
  
### <a name="to-publish-to-a-cd-rom-or-dvd-rom"></a>Chcete-li publikovat na disku CD-ROM nebo DVD-ROM  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt aplikace a klikněte na **vlastnosti**.  
  
     **Návrhář projektu** se zobrazí.  
  
2.  Klikněte na tlačítko **publikovat** otevřete **publikovat** stránky v **Návrhář projektu**a klikněte na tlačítko **Průvodci publikováním** tlačítko.  
  
     Zobrazí se v Průvodci publikováním.  
  
3.  V **kde chcete publikovat aplikaci?** stránky, zadejte cestu k souboru nebo umístění FTP, kde bude aplikace publikována, d:\deploy. Pak klikněte na tlačítko **Další** pokračujte.  
  
4.  Na **jak budou uživatelé aplikaci instalovat?** stránky, klikněte na položku **disku CD-ROM nebo DVD-ROM**a potom klikněte na **Další**.  
  
    > [!NOTE]
    >  Pokud chcete instalaci spustit automaticky při disku CD-ROM je vložen do jednotky, otevřete **publikovat** stránku **Návrhář projektu** a klikněte na tlačítko **možnosti** tlačítko a pak na **možnosti publikování** průvodci vyberte **instalace z disku CD pro automaticky spustit instalační program, pokud je disk CD-ROM**.  
  
5.  Pokud distribuujete aplikace, můžete k poskytování aktualizací z webu. V **kde bude aplikace vyhledávat aktualizace?** stránky, zvolte možnost aktualizace:  
  
    -   Pokud aplikace bude vyhledávat aktualizace, klikněte na tlačítko **bude aplikace vyhledávat aktualizace z následujícího umístění** a zadejte umístění, kam budou zasílány aktualizace. To může být umístění souboru, web nebo FTP server.  
  
    -   Pokud aplikace nebude aktualizace vyhledávat, klikněte na tlačítko **aplikace nebude aktualizace vyhledávat**.  
  
     Klikněte na tlačítko **Další** pokračujte.  
  
6.  Klikněte na tlačítko **Dokončit** k publikování aplikace.  
  
     Stav publikování se zobrazí v oznamovací oblasti stav.  
  
    > [!NOTE]
    >  Po dokončení publikování budete muset použít CD-RW nebo DVD-RW zkopírovat soubory z umístění zadané v kroku 3 na disku CD-ROM nebo DVD-ROM médium.  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Nasazení řešení Office s použitím technologie ClickOnce](/office-dev/office-dev/deploying-an-office-solution-by-using-clickonce)