---
title: 'Postupy: Povolení funkce AutoStart pro instalace z disku CD | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
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
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6266f487e2e0c66e532297c3fdae3fd3e5498052
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54777759"
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>Postupy: Povolení funkce AutoStart pro instalace z disku CD
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při nasazování [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace pomocí vyměnitelného média jako je například disk CD-ROM nebo DVD-ROM, můžete povolit `AutoStart` tak, aby [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace se automaticky spustí, když je médium je vloženo.  
  
 `AutoStart` lze povolit **publikovat** stránku **Návrháře projektu**.  
  
### <a name="to-enable-autostart"></a>Povolit automatické spuštění  
  
1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** klikněte na nabídku **vlastnosti**.  
  
2.  Klikněte na tlačítko **publikovat** kartu.  
  
3.  Klikněte na tlačítko **možnosti** tlačítko.  
  
     **Možnosti publikování** zobrazí se dialogové okno.  
  
4.  Klikněte na tlačítko **nasazení**.  
  
5.  Vyberte **pro instalace z CD automaticky spustit instalační program po vložení disku CD** zaškrtávací políčko.  
  
     Soubor Autorun.inf budou zkopírovány do umístění pro publikování, když je aplikace publikována.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
