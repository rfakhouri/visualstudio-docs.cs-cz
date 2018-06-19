---
title: 'Postupy: povolení funkce AutoStart pro instalace z disku CD | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, AutoStart
- ClickOnce deployment, installation on CD or DVD
- deploying applications [ClickOnce], installation on CD or DVD
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 230f0491993b3804c3147e727900de2647ff7bda
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31558240"
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>Postupy: Povolení funkce AutoStart pro instalace z média CD
Při nasazování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci prostřednictvím vyměnitelných médií jako jsou jednotky CD-ROM nebo DVD-ROM, můžete povolit `AutoStart` tak, aby [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se automaticky spustí, když vložení média.  
  
 `AutoStart` můžete povolit pro **publikovat** stránky **Návrhář projektu**.  
  
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
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)