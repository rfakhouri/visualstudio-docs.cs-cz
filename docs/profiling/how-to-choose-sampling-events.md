---
title: 'Postupy: Výběr událostí vzorkování | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3d3562f446ebbc5f6e24ce9911ff9e09daa04e55
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621315"
---
# <a name="how-to-choose-sampling-events"></a>Postupy: Výběr událostí vzorkování
Ve výchozím nastavení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů pro profilaci sady shromažďuje údaje o výkonu v intervalu, který je zadán jako počet cyklů procesoru, které jsou používány profilovaný proces. Výchozí počet cyklů v intervalu je 10 000 000, což je na 1 počítači gv přibližně na 0,01 sekund. Počet cyklů v intervalu můžete změnit, a můžete změnit událost vzorku. Následující ukázkové události jsou k dispozici:

-   Hodinových cyklů - problémů vázané na procesor.

-   Chyby stránek – pro problémy související s pamětí.

-   Systémová volání - I O souvisejícím s/problémů.

-   Čítač výkonu – čítače CPU pro problémy výkonu na nízké úrovni.

> [!IMPORTANT]
>  Pokud pomocí metody vzorkování se shromažďování dat paměti .NET (přidělení správu životnosti objektů nebo obojí), jsou ignorovány všechny zadané uživatelem vzorkování událostí a přidělení paměti odpovídající události kolekce paměti nebo obojí, se používá ke shromažďování dat.

### <a name="to-select-a-sample-event"></a>Vybrat událost vzorku

1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na relaci výkonu a pak klikněte na tlačítko **vlastnosti**.

2.  V **stránky vlastností**, klikněte na tlačítko **vzorkování** vlastnosti.

3.  Z **událost vzorku** rozevíracího seznamu vyberte událost vzorku, kterou chcete použít pro profilování aplikace.

    > [!NOTE]
    >  **Dostupných čítačů výkonu** jsou povolené jenom v případě, že vyberete **čítač výkonu** z **událost vzorku** rozevíracího seznamu.

4.  Pokud vyberete **čítač výkonu**, vyberte konkrétní čítač procesoru z **dostupných čítačů výkonu** ovládací prvek zobrazení stromové struktury.

    -   Hodnoty čítačů **události přenositelnosti** uzlu jsou k dispozici na všech typech procesory.

    -   Hodnoty čítačů **události platformy** uzlu jsou specifické pro procesor na aktuálním počítači a nemusí být k dispozici na jiných typů procesory.

5.  Když vyberete událost vzorku, výchozí hodnota intervalu vzorkování se zobrazí v **interval vzorkování** textového pole. V případě potřeby můžete zadat hodnotu, která má v textovém poli.

## <a name="see-also"></a>Viz také:
- [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
- [Postupy: Výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)
- [Čítače procesoru a systému Windows](../profiling/cpu-and-windows-counters.md)
- [Vysvětlení hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)
- [Profil z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)