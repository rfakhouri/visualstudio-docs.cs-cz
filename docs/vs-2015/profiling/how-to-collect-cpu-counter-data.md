---
title: 'Postupy: Shromažďování dat čítačů procesoru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.cpucounters
helpviewer_keywords:
- profiling tools, using portable CPU counters
- performance tools, portable CPU counters
ms.assetid: 102fb6ca-5fbf-4b05-925f-56912ce3f44b
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b197bbc434ecf01ad5b6df332530ad719575aede
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60104080"
---
# <a name="how-to-collect-cpu-counter-data"></a>Postupy: Shromažďování dat čítačů procesoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Čítače procesoru událostí se používá ke shromažďování dat výkonu hardwaru. Toto téma ukazuje, jak shromažďovat data událostí, použijete-li metoda profilace instrumentace.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
  Dva typy událostí čítače CPU dojít:  
  
- Události přenositelnosti - procesoru událostí, které se můžou shromažďovat, bez ohledu na konkrétním procesoru.  
  
- Události platformy – procesoru událostí, které jsou spojeny s konkrétním procesoru.  
  
  Události přenositelnosti zahrnují obecné události, jako je vyřazeno pokyny a bez zastavení cykly, události vyrovnávací paměť procesoru, větvení události a události mezipaměti L2. Čítače událostí dostupné platformy jsou určeny výrobce procesoru.  
  
  Kategorie událostí, které mohou být sdíleny platformu a přenosné čítače. Například následující kategorie dat jsou často společné pro oba typy:  
  
- Události paměti.  
  
- Přední události.  
  
- Události větvě.  
  
  Můžete shromažďovat data čítačů výkonu v Profiler dvěma způsoby:  
  
- Shromažďování dat z jednoho nebo více čítačů při profilování instrumentace.  
  
- Při profilování pomocí vzorkování, zadáte jako interval vzorkování čítače událostí. Další informace najdete v tématu [jak: Výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md).  
  
### <a name="to-collect-cpu-performance-counter-data-when-you-profile-by-instrumentation"></a>Ke shromažďování dat čítače výkonu procesoru při profilování instrumentace  
  
1. V relaci výkonu **stránky vlastností**, klikněte na tlačítko **čítače CPU.**  
  
2. Vyberte **shromáždit čítače CPU** zaškrtávací políčko.  
  
3. Rozbalte **dostupných čítačů výkonu** stromové struktury, dokud nenajdete ukázkové události, které chcete shromažďovat.  
  
4. Pro každou událost, která chcete shromažďovat, vyberte události a pak klikněte na tlačítko se šipkou doprava přidejte událost, abyste **vybrané čítače** seznamu.  
  
    > [!NOTE]
    >  **Dostupné čítače výkonu** je povolená jenom v případě, že jste vybrali **čítače CPU shromažďovat** zaškrtávací políčko.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)   
 [Využití procesoru a čítače Windows](../profiling/cpu-and-windows-counters.md)   
 [Postupy: Výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md)
