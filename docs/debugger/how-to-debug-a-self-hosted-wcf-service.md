---
title: 'Postupy: Ladění služby WCF v místním prostředí | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
ms.openlocfilehash: 1a847071fa62e0ae168a5c830bd7f52a80edf740
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956124"
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>Postupy: Ladění služby WCF v místním prostředí
A *služby v místním prostředí* je služba WCF, která není spuštěna služba IIS, hostitel služby WCF nebo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] vývojový Server. Nejjednodušší způsob, jak ladit WCF s vlastním hostováním, je konfigurace [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ke spuštění klienta i serveru, když zvolíte **spustit ladění** na **ladění** nabídky.  
  
 Tuto metodu nelze použít, pokud je služba WCF s vlastním hostováním uvnitř procesu, který nelze spustit tímto způsobem, jako je služba NT. Místo toho lze provést jednu z následujících možností:  
  
-   Ladicí program k hostitelskému procesu připojit ručně. Další informace najdete v tématu [připojení k běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
     – nebo –  
  
-   Spustit ladění klientu a poté krokovat s vnořením volání služby. To vyžaduje povolení ladění v souboru app.config. Další informace najdete [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>Spuštění klientu a hostitele v systému Visual Studio  
  
1. Vytvořte řešení systému [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], které obsahuje projekty klientu i serveru.  
  
2. Konfigurace řešení, aby procesy klienta a serveru při výběru **Start** na **ladění** nabídky.  
  
   1.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na název řešení.  
  
   2.  Klikněte na tlačítko **nastavit projekty po spuštění**.  
  
   3.  V **řešení \<name > vlastnosti** dialogu **více projektů po spuštění**.  
  
   4.  V **více projektů po spuštění** mřížky na řádek, který odpovídá projektu serveru, klikněte na tlačítko **akce** a zvolte **Start**.  
  
   5.  Na řádku, který odpovídá projektu klientu, klikněte na tlačítko **akce** a zvolte **Start**.  
  
   6.  Klikněte na **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění služeb WCF](../debugger/debugging-wcf-services.md)   
 [Omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md)   
 [Postupy: Krokování s vnořením služeb WCF](../debugger/how-to-step-into-wcf-services.md)