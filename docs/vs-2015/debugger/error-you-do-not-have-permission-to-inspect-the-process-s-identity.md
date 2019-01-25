---
title: 'Chyba: Nemáte oprávnění ke kontrole procesu&#39;s identity | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 6233d060-85b8-42be-ae5f-bde7e1d0f241
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f173be87987cbc8bcfb3390dfdaaf5eab7501bb6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54776215"
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Chyba: Nemáte oprávnění ke kontrole procesu&#39;s identity
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
