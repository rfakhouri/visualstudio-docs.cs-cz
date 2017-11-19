---
title: "Postupy: povolení funkce AutoStart pro instalace z disku CD | Microsoft Docs"
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
- ClickOnce deployment, AutoStart
- ClickOnce deployment, installation on CD or DVD
- deploying applications [ClickOnce], installation on CD or DVD
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: e3656c3d32dcba946cf66d7fba56a68b3de467f6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>Postupy: Povolení funkce AutoStart pro instalace z média CD
Při nasazování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci prostřednictvím vyměnitelných médií jako jsou jednotky CD-ROM nebo DVD-ROM, můžete povolit `AutoStart` tak, aby [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se automaticky spustí, když vložení média.  
  
 `AutoStart`můžete povolit pro **publikovat** stránky **Návrhář projektu**.  
  
### <a name="to-enable-autostart"></a>Chcete-li povolit automatické spuštění  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídce klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte **možnosti** tlačítko.  
  
     **Možnosti publikování** zobrazí se dialogové okno.  
  
4.  Klikněte na tlačítko **nasazení**.  
  
5.  Vyberte **instalace z disku CD pro automaticky spustit instalační program, pokud je disk CD-ROM** zaškrtávací políčko.  
  
     Soubor Autorun.inf budou zkopírovány do umístění pro publikování, když je aplikace publikována.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)