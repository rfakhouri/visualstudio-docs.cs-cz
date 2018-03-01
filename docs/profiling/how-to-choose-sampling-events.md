---
title: "Postupy: výběr událostí vzorkování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.sampling
helpviewer_keywords:
- clock cycles sample event
- sample events, choosing
- profiling tools, sample events
- page faults sample event
- system calls sample event
- performance counter sample event
- performance tools, sample events
ms.assetid: ce7cb734-80ac-4930-a4ef-e24395e1cc07
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8475544d6ecb822a25a423b73543d7364d79da10
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-choose-sampling-events"></a>Postupy: Výběr událostí vzorkování
Ve výchozím nastavení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci shromažďuje údaje o výkonu na časový interval, který je zadán jako počet cyklů procesoru, které jsou používány PROFILOVANÉHO proces. Výchozí počet cyklů v intervalu je 10 000 000, což je přibližně 0,01 sekund na 1 GH počítači. Můžete změnit počet cyklů v intervalu a můžete změnit událost vzorku. Následující ukázkové události jsou k dispozici:  
  
-   Hodiny cykly - problémů vázané na procesor.  
  
-   Chyby stránek - pro problémy související s pamětí.  
  
-   Systémová volání - I/E-související problémy.  
  
-   Čítač výkonu - čítače CPU pro problémy s výkonem nižší úrovně.  
  
> [!IMPORTANT]
>  Pokud se shromažďování dat paměti .NET (přidělení nebo životnosti objektu nebo obě) pomocí metody vzorkování, jsou ignorovány všechny zadán uživatel vzorkování události a přidělení odpovídající paměti nebo události uvolňování paměti nebo obojí, se používá ke shromažďování dat.  
  
### <a name="to-select-a-sample-event"></a>Chcete-li vybrat událost vzorku  
  
1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.  
  
2.  V **stránky vlastností**, klikněte **vzorkování** vlastnosti.  
  
3.  Z **událost vzorku** rozevíracího seznamu vyberte událost vzorku, který chcete použít pro profil aplikace.  
  
    > [!NOTE]
    >  **Čítače výkonu k dispozici** jsou povoleny pouze v případě, že vyberete **čítače výkonu** z **událost vzorku** rozevíracího seznamu.  
  
4.  Pokud vyberete **čítače výkonu**, vyberte konkrétní čítačů procesoru z **čítače výkonu k dispozici** stromové zobrazení ovládacího prvku.  
  
    -   Čítače **přenosné události** uzlu jsou k dispozici na všech typech procesory.  
  
    -   Čítače **události platformy** uzlu jsou specifické pro procesor v počítači a nemusí být k dispozici na jiné typy procesorů.  
  
5.  Když vyberete událost vzorku, zobrazí se výchozí hodnota intervalu vzorkování v **intervalu vzorkování** textové pole. V případě potřeby můžete zadat hodnotu, která chcete v textovém poli.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Postupy: výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)   
 [Využití procesoru a čítačů systému Windows](../profiling/cpu-and-windows-counters.md)   
 [Porozumění hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)   
 [Profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)