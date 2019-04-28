---
title: Okno Prohlížeč výkonu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performanceexplorer
- vs.performance.explorer
helpviewer_keywords:
- performance tools, Performance Explorer
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c8ffa5340ceaa00adb5e86100d8e58c307f41d40
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62794431"
---
# <a name="performance-explorer-window"></a>Okno Prohlížeč výkonu

**Prohlížeč výkonu** okno v integrovaném vývojovém prostředí sady Visual Studio umožňuje konfiguraci a spuštění relace výkonu pomocí nástrojů profilování Visual Studio. Pokud je potřeba otevřít okno, postupujte podle pokynů v [začátečníky Průvodce profilací výkonu](../profiling/beginners-guide-to-cpu-sampling.md).

## <a name="performance-explorer-toolbar"></a>Panel nástrojů Průzkumník výkonu

Tyto možnosti jsou k dispozici na **prohlížeč výkonu** nástrojů:

- **Spustit Průvodce výkonem** -zobrazí Průvodce výkonu a přidat novou relaci výkonu v okně Průzkumník výkonu.

- **Novou relaci výkonu** – přidá prázdný výkonnostní relaci v okně Průzkumník výkonu.

- **Spuštění** – **spuštění** příkaz seznamu umožňuje spustit cílovou aplikaci, která má, okamžitě povolená profilace (**spustit s nástrojem pro profilaci**) nebo pozastavené (profilací **Pozastaví spuštění profilací**).

- **Metoda** – Určuje, jestli je metodu relace profilace vzorkování nebo instrumentace.

- **Zastavit** – okamžitě ukončí cílové aplikace a profiler.

- **Attach/Detach** – zobrazí **připojit Profiler k procesu** dialogové okno Vybrat spuštěný proces, ke kterému chcete připojit profiler.

## <a name="performance-explorer-window"></a>Okno Prohlížeč výkonu

**Prohlížeč výkonu** okno obsahuje ovládací prvek stromu, který zobrazuje binární soubory a soubory data sestav z jednoho nebo více výkonnostních relací.

- **Název relace** – kořenový adresář ovládacího prvku strom obsahuje název relace. Klikněte pravým tlačítkem na název relace, můžete nastavit vlastnosti relace nebo spustit cílovou aplikaci a profiler.

- **Cíle** -zobrazí názvy binárních souborů, které se má být profilována v relaci. Klikněte pravým tlačítkem na **cíle** s přidáváním a odebíráním binární soubor, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu nebo Web. Klikněte pravým tlačítkem na název cílového nastavení vlastností pro jednotlivé binárního souboru.

- **Sestavy** – zobrazuje názvy souborů dat profileru, které jsou generovány pro relaci. Klikněte pravým tlačítkem na **sestavy** můžete přidat existující sestavy nebo porovnání dvou souborů dat profileru. Klikněte pravým tlačítkem na název sestavy, čímž otevřete, odebrat nebo exportovat datového souboru profilování.

## <a name="see-also"></a>Viz také:

[Přehledy](../profiling/overviews-performance-tools.md)
[konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
[řízení sběru dat](../profiling/controlling-data-collection.md)