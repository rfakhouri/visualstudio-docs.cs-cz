---
title: 'Postupy: shromažďování dat čítačů procesoru | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.property.cpucounters
helpviewer_keywords:
- profiling tools, using portable CPU counters
- performance tools, portable CPU counters
ms.assetid: 102fb6ca-5fbf-4b05-925f-56912ce3f44b
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8f7c9f88dbbc3d7d2022736528f2b35fa3a325b1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674313"
---
# <a name="how-to-collect-cpu-counter-data"></a>Postupy: Shromažďování dat čítačů procesoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: shromažďování dat čítačů procesoru](https://docs.microsoft.com/visualstudio/profiling/how-to-collect-cpu-counter-data).  
  
Čítače procesoru událostí se používá ke shromažďování dat výkonu hardwaru. Toto téma ukazuje, jak shromažďovat data událostí, použijete-li metoda profilace instrumentace.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
 Dva typy událostí čítače CPU dojít:  
  
-   Události přenositelnosti - procesoru událostí, které se můžou shromažďovat, bez ohledu na konkrétním procesoru.  
  
-   Události platformy – procesoru událostí, které jsou spojeny s konkrétním procesoru.  
  
 Události přenositelnosti zahrnují obecné události, jako je vyřazeno pokyny a bez zastavení cykly, události vyrovnávací paměť procesoru, větvení události a události mezipaměti L2. Čítače událostí dostupné platformy jsou určeny výrobce procesoru.  
  
 Kategorie událostí, které mohou být sdíleny platformu a přenosné čítače. Například následující kategorie dat jsou často společné pro oba typy:  
  
-   Události paměti.  
  
-   Přední události.  
  
-   Události větvě.  
  
 Můžete shromažďovat data čítačů výkonu v Profiler dvěma způsoby:  
  
-   Shromažďování dat z jednoho nebo více čítačů při profilování instrumentace.  
  
-   Při profilování pomocí vzorkování, zadáte jako interval vzorkování čítače událostí. Další informace najdete v tématu [jak: Zvolte událostí vzorkování](../profiling/how-to-choose-sampling-events.md).  
  
### <a name="to-collect-cpu-performance-counter-data-when-you-profile-by-instrumentation"></a>Ke shromažďování dat čítače výkonu procesoru při profilování instrumentace  
  
1.  V relaci výkonu **stránky vlastností**, klikněte na tlačítko **čítače CPU.**  
  
2.  Vyberte **shromáždit čítače CPU** zaškrtávací políčko.  
  
3.  Rozbalte **dostupných čítačů výkonu** stromové struktury, dokud nenajdete ukázkové události, které chcete shromažďovat.  
  
4.  Pro každou událost, která chcete shromažďovat, vyberte události a pak klikněte na tlačítko se šipkou doprava přidejte událost, abyste **vybrané čítače** seznamu.  
  
    > [!NOTE]
    >  **Dostupné čítače výkonu** je povolená jenom v případě, že jste vybrali **čítače CPU shromažďovat** zaškrtávací políčko.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)   
 [Využití procesoru a čítače Windows](../profiling/cpu-and-windows-counters.md)   
 [Postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md)



