---
title: 'Postupy: Krokování s vnořením služeb WCF | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging
ms.assetid: 9893ad01-54af-499f-85a6-9d1cfe6eb640
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 951d5f39fbf3929d094cc18de5fe108b46753b09
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60056442"
---
# <a name="how-to-step-into-wcf-services"></a>Postupy: Krokování s vnořením služeb WCF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], můžete krokovat s vnořením služeb WCF. Pokud je služba WCF v rámci stejného [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] řešení jako klient, může dosažení zarážky ve službě WCF.  
  
 Pro krokování na práci, musíte mít ladění povoleno v souboru Web.config nebo app.config. Informace o tom, jak povolit ladění a omezení krokování s vnořením služeb WCF, naleznete v tématu [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-step-into-a-wcf-service"></a>Chcete-li krokovat s vnořením služeb WCF  
  
1. Vytvoření [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] řešení, které obsahuje klienta WCF a projekty služeb WCF.  
  
2. V Průzkumníku řešení klikněte pravým tlačítkem na projekt klienta WCF a potom klikněte na tlačítko **nastavit jako spouštěný projekt**.  
  
3. Povolte ladění v souboru app.config nebo web.config. Další informace najdete v tématu [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
4. Nastavte zarážku na umístění v klientském projektu, ve kterém chcete spustit krokování. Obvykle to bude bezprostředně před volání služby WCF.  
  
5. Spusťte zarážku a pak začít krokování. Ladicí program bude automaticky krokovat do služby.  
  
## <a name="see-also"></a>Viz také  
 [Ladění služeb WCF](../debugger/debugging-wcf-services.md)   
 [Omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md)   
 [Postupy: Ladění služby WCF s vlastním hostováním](../debugger/how-to-debug-a-self-hosted-wcf-service.md)
