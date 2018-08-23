---
title: 'Postupy: ladění služby WCF v místním prostředí | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1e87af205a88e84942eb4958876c2030a175065
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676123"
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>Postupy: Ladění služby WCF s vlastním hostováním
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: ladění služby WCF s místním](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-a-self-hosted-wcf-service).  
  
A *služby v místním prostředí* je služba WCF, která není spuštěna služba IIS, hostitel služby WCF nebo [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] vývojový Server. Nejjednodušší způsob, jak ladit WCF s vlastním hostováním, je konfigurace [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ke spuštění klienta i serveru, když zvolíte **spustit ladění** na **ladění** nabídky.  
  
 Tuto metodu nelze použít, pokud je služba WCF s vlastním hostováním uvnitř procesu, který nelze spustit tímto způsobem, jako je služba NT. Místo toho lze provést jednu z následujících možností:  
  
-   Ladicí program k hostitelskému procesu připojit ručně. Další informace najdete v tématu [připojení k běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
     – nebo –  
  
-   Spustit ladění klientu a poté krokovat s vnořením volání služby. To vyžaduje povolení ladění v souboru app.config. Další informace najdete [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>Spuštění klientu a hostitele v systému Visual Studio  
  
1.  Vytvořte řešení systému [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], které obsahuje projekty klientu i serveru.  
  
2.  Konfigurace řešení, aby procesy klienta a serveru při výběru **Start** na **ladění** nabídky.  
  
    1.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na název řešení.  
  
    2.  Klikněte na tlačítko **nastavit projekty po spuštění**.  
  
    3.  V **řešení \<name > vlastnosti** dialogu **více projektů po spuštění**.  
  
    4.  V **více projektů po spuštění** mřížky na řádek, který odpovídá projektu serveru, klikněte na tlačítko **akce** a zvolte **Start**.  
  
    5.  Na řádku, který odpovídá projektu klientu, klikněte na tlačítko **akce** a zvolte **Start**.  
  
    6.  Klikněte na tlačítko **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění služeb WCF](../debugger/debugging-wcf-services.md)   
 [Omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md)   
 [Postupy: krokování s vnořením služeb WCF](../debugger/how-to-step-into-wcf-services.md)



