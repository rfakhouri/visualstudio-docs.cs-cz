---
title: "Okno Prohlížeč výkonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performanceexplorer
- vs.performance.explorer
helpviewer_keywords: performance tools, Performance Explorer
ms.assetid: cb6a6efc-93a5-49a2-8d03-6969b5f3b6d7
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3ab16dca3d4d27c157620f59774ec37f57aae020
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="performance-explorer-window"></a>Okno Prohlížeč výkonu
**Prohlížeč výkonu** okno v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) umožňuje nakonfigurovat a spustit výkonnostních relací s použitím [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
## <a name="performance-explorer-toolbar"></a>Panel nástrojů výkonu aplikace Explorer  
 Tyto možnosti jsou dostupné na **prohlížeč výkonu** nástrojů:  
  
-   **Spustí Průvodce výkonu** -zobrazí výkonu průvodce a přidejte novou relaci výkonu do okna Prohlížeč výkonu.  
  
-   **Novou relaci výkonu** -přidá relaci prázdný výkonu okno Prohlížeč výkonu.  
  
-   **Spusťte** – **spusťte** příkaz seznam umožňuje spustit cílové aplikace, která profilace okamžitě povolené (**spouštění profilace**) nebo s profilace pozastavenou ( **Spuštění s profilace pozastavena**).  
  
-   **Metoda** -Určuje, zda je relace profilování metoda vzorkování nebo instrumentace.  
  
-   **Zastavit** -okamžitě ukončí cílová aplikace a profileru.  
  
-   **Attach/Detach** -zobrazí **připojit profileru proces** dialogové okno Vybrat spuštěných procesů, ke kterému chcete připojit profileru.  
  
## <a name="performance-explorer-window"></a>Okno Prohlížeč výkonu  
 **Prohlížeč výkonu** okno obsahuje ovládací prvek stromu, která zobrazuje binární soubory a data souborů sestav z jednoho nebo více výkonnostních relací.  
  
-   **Název relace** -kořenovém ovládací prvek stromu obsahuje název relace. Klikněte pravým tlačítkem na název relace nastavit vlastnosti relace nebo spusťte cílová aplikace a profileru.  
  
-   **Cíle** -zobrazuje názvy binární soubory, které mají být profilovaným v relaci. Klikněte pravým tlačítkem na **cíle** přidat nebo odebrat binární, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu nebo webu. Klikněte pravým tlačítkem na název cílového nastavení vlastností pro jednotlivé binárního souboru.  
  
-   **Sestavy** -zobrazuje názvy datových souborů profileru, které jsou generovány pro relaci. Klikněte pravým tlačítkem na **sestavy** přidat existující sestavu nebo porovnat dva datových souborů profileru. Klikněte pravým tlačítkem na název sestavy můžete otevřít, odebrat nebo exportovat soubor dat profileru.  
  
## <a name="see-also"></a>Viz také  
 [Přehled](../profiling/overviews-performance-tools.md)   
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Řízení shromažďování dat](../profiling/controlling-data-collection.md)