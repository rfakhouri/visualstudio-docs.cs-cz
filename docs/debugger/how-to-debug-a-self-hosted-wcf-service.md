---
title: 'Postupy: ladění služby WCF s vlastním hostováním | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb1fcd61c65b29a0ccb262b31a10847ebb80539d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>Postupy: Ladění služby WCF s vlastním hostováním
A *hostovanou na vlastním* je služba WCF, která není spuštěna v IIS, hostitel služby WCF, nebo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] vývojový Server. Nejjednodušší způsob, jak ladit vlastním hostováním WCF je konfigurace [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ke spuštění klienta i serveru, když zvolíte **spustit ladění** na **ladění** nabídky.  
  
 Tuto metodu nelze použít, pokud je služba WCF s vlastním hostováním uvnitř procesu, který nelze spustit tímto způsobem, jako je služba NT. Místo toho lze provést jednu z následujících možností:  
  
-   Ladicí program k hostitelskému procesu připojit ručně. Další informace najdete v tématu [přiřadit běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
     – nebo –  
  
-   Spustit ladění klientu a poté krokovat s vnořením volání služby. To vyžaduje povolení ladění v souboru app.config. Další informace najdete [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>Spuštění klientu a hostitele v systému Visual Studio  
  
1.  Vytvořte řešení systému [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], které obsahuje projekty klientu i serveru.  
  
2.  Nakonfigurujte řešení, aby klient i server procesy spustit, když zvolíte **spustit** na **ladění** nabídky.  
  
    1.  V **Průzkumníku**, klikněte pravým tlačítkem na název řešení.  
  
    2.  Klikněte na tlačítko **nastavení projektů po spuštění**.  
  
    3.  V **řešení \<name > vlastnosti** dialogové okno, vyberte **více projektů po spuštění**.  
  
    4.  V **více projektů po spuštění** mřížky na řádek, který odpovídá serverový projekt, klikněte na tlačítko **akce** a zvolte **spustit**.  
  
    5.  V řádku, která odpovídá projektu klienta, klikněte na tlačítko **akce** a zvolte **spustit**.  
  
    6.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění služby WCF](../debugger/debugging-wcf-services.md)   
 [Omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md)   
 [Postupy: krokování s vnořením služeb WCF](../debugger/how-to-step-into-wcf-services.md)