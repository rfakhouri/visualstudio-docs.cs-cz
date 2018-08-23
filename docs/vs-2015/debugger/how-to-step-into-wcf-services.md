---
title: 'Postupy: krokování s vnořením služeb WCF | Dokumentace Microsoftu'
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
- WCF, debugging
ms.assetid: 9893ad01-54af-499f-85a6-9d1cfe6eb640
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b779c8bc2e6da3975f1f70265482c706c9141375
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668684"
---
# <a name="how-to-step-into-wcf-services"></a>Postupy: Krokování s vnořením služeb WCF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: krokování s vnořením služeb WCF](https://docs.microsoft.com/visualstudio/debugger/how-to-step-into-wcf-services).  
  
V [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], můžete krokovat s vnořením služeb WCF. Pokud je služba WCF v rámci stejného [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] řešení jako klient, může dosažení zarážky ve službě WCF.  
  
 Pro krokování na práci, musíte mít ladění povoleno v souboru Web.config nebo app.config. Informace o tom, jak povolit ladění a omezení krokování s vnořením služeb WCF, naleznete v tématu [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-step-into-a-wcf-service"></a>Chcete-li krokovat s vnořením služeb WCF  
  
1.  Vytvoření [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] řešení, které obsahuje klienta WCF a projekty služeb WCF.  
  
2.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt klienta WCF a potom klikněte na tlačítko **nastavit jako spouštěný projekt**.  
  
3.  Povolte ladění v souboru app.config nebo web.config. Další informace najdete v tématu [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
4.  Nastavte zarážku na umístění v klientském projektu, ve kterém chcete spustit krokování. Obvykle to bude bezprostředně před volání služby WCF.  
  
5.  Spusťte zarážku a pak začít krokování. Ladicí program bude automaticky krokovat do služby.  
  
## <a name="see-also"></a>Viz také  
 [Ladění služeb WCF](../debugger/debugging-wcf-services.md)   
 [Omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md)   
 [Postupy: ladění služby WCF v místním prostředí](../debugger/how-to-debug-a-self-hosted-wcf-service.md)



