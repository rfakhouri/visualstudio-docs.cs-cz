---
title: "Chyba: Nemáte oprávnění ke kontrole proces & č. 39; s identity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f51087d4f7882c34826942a898328640107a5ac6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Chyba: Nemáte oprávnění ke kontrole proces & č. 39; s identity
Nemáte oprávnění ke kontrole identity procesu. To může být způsobeno konfiguraci vašeho systému.  
  
 Ladicí program nemohl ke kontrole identity procesu, což je potřebné informace pro ladění. Nejpravděpodobnější příčinou je zakázaná Terminálové služby. Ve výchozím nastavení je povolena služba Terminálové služby. Postupujte podle těchto kroků můžete znovu povolit.  
  
### <a name="to-enable-terminal-services"></a>Chcete-li povolit Terminálové služby  
  
1.  Klikněte na tlačítko **spustit** a potom zvolte **ovládací panely**.  
  
2.  V Ovládacích panelech vyberte **přepnout do klasického zobrazení**, v případě potřeby a potom dvakrát klikněte na **nástroje pro správu**.  
  
3.  V **nástroje pro správu** okna, klikněte dvakrát na **Správa počítače**.  
  
4.  V okně Správa počítače, rozbalte **služeb a aplikací** uzlu.  
  
5.  V části **služeb a aplikací**, klikněte na tlačítko **služby**.  
  
     V pravém podokně se zobrazí seznam služeb.  
  
6.  V **služby** seznamu, klikněte pravým tlačítkem na **Terminálové služby** a potom zvolte **vlastnosti**.  
  
7.  V **Terminálové služby vlastnosti** okno, přejděte na **Obecné** kartě a nastavte **typ spuštění** k **ruční**.  
  
8.  Click **OK**.  
  
9. Restartujte počítač.  
  
     Tento postup nepovolí automaticky vzdálené plochy. Pokud chcete povolit vzdálené plochy ve vašem počítači, proveďte následující další postup.  
  
### <a name="to-enable-remote-desktop"></a>Chcete-li povolit vzdálená plocha  
  
1.  Klikněte na tlačítko **spustit** a potom klikněte pravým tlačítkem na **Můj počítač**.  
  
2.  Zvolte **vlastnosti**.  
  
     **Vlastnosti systému** zobrazí se okno.  
  
3.  Klikněte na tlačítko **vzdáleného**.  
  
4.  V části **vzdálené plochy**, vyberte **povolit uživatelům vzdálené připojení k tomuto počítači**.  
  
5.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)