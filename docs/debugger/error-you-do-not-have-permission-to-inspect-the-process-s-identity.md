---
title: 'Chyba: Nemáte oprávnění ke kontrole procesu&#39;s identity | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2424379a016a80d251b53e79799fd0d39e059218
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53941859"
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Chyba: Nemáte oprávnění ke kontrole procesu&#39;s identity
Nemáte oprávnění ke kontrole identity procesu. To může být způsobeno konfiguraci vašeho systému.  
  
 Ladicí program nemohl ke kontrole identity procesu, což je nezbytné informace pro ladění. Nejpravděpodobnější příčinou je Terminálové služby, protože se zakázalo. Ve výchozím nastavení je povolená Terminálová služba služby. Následujícím postupem ji znovu povolit.  
  
### <a name="to-enable-terminal-services"></a>Chcete-li povolit Terminálové služby  
  
1.  Klikněte na tlačítko **Start** a klikněte na tlačítko **ovládací panely**.  
  
2.  V Ovládacích panelech zvolte **přepnout do klasického zobrazení**, v případě potřeby a potom dvakrát klikněte na panel **nástroje pro správu**.  
  
3.  V **nástroje pro správu** okna, dvakrát klikněte na panel **Správa počítače**.  
  
4.  V okně Správa počítače, rozbalte **služeb a aplikací** uzlu.  
  
5.  V části **služeb a aplikací**, klikněte na tlačítko **služby**.  
  
     V pravém podokně se zobrazí seznam služeb.  
  
6.  V **služby** seznamu, klikněte pravým tlačítkem na **Terminálové služby** a klikněte na tlačítko **vlastnosti**.  
  
7.  V **Terminálové služby vlastnosti** okno, přejděte na **Obecné** kartě a nastavte **typ spouštění** k **ruční**.  
  
8.  Klikněte na **OK**.  
  
9. Restartujte počítač.  
  
     Tento postup neumožňuje automaticky vzdálené plochy. Pokud chcete povolit vzdálenou plochu v počítači, následujícím postupem Další.  
  
### <a name="to-enable-remote-desktop"></a>Chcete-li povolit vzdálenou plochu  
  
1.  Klikněte na tlačítko **Start** a potom klikněte pravým tlačítkem na **tento počítač**.  
  
2.  Zvolte **vlastnosti**.  
  
     **Vlastnosti systému** se zobrazí okno.  
  
3.  Klikněte na tlačítko **vzdálené**.  
  
4.  V části **vzdálené plochy**vyberte **umožňují uživatelům vzdálené připojení k tomuto počítači**.  
  
5.  Klikněte na **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)