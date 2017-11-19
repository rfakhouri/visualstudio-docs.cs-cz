---
title: "Postupy: krokování s vnořením služeb WCF | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging
ms.assetid: 9893ad01-54af-499f-85a6-9d1cfe6eb640
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6aeaba831bb82731ae7d3e62cbff5190bb474357
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-step-into-wcf-services"></a>Postupy: Krokování s vnořením služeb WCF
V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], můžete krok do služby WCF. Pokud je služba WCF ve stejné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení jako klient, může dosáhl zarážky uvnitř služby WCF.  
  
 Pro krokování s k práci, musí mít v souboru Web.config nebo app.config povoleno ladění. Informace o tom, jak povolit ladění a omezení krokování s vnořením služeb WCF, najdete v části [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-step-into-a-wcf-service"></a>Pro krok do služby WCF  
  
1.  Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, který obsahuje klienta WCF a projekty služeb WCF.  
  
2.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt klienta WCF a pak klikněte na tlačítko **nastavit jako spouštěný projekt**.  
  
3.  Povolte ladění v souboru app.config nebo web.config. Další informace najdete v tématu [omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md).  
  
4.  Nastavte zarážky v projektu klienta do umístění, kde chcete spustit krokování s. Obvykle to bude bezprostředně před volání služby WCF.  
  
5.  Spusťte na zarážku, a poté zahájit krokování s. Ladicí program bude automaticky krok do služby.  
  
## <a name="see-also"></a>Viz také  
 [Ladění služby WCF](../debugger/debugging-wcf-services.md)   
 [Omezení ladění WCF](../debugger/limitations-on-wcf-debugging.md)   
 [Postupy: ladění služby WCF s vlastním hostováním](../debugger/how-to-debug-a-self-hosted-wcf-service.md)