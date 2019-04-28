---
title: 'Postupy: Shromažďování dat čítačů Windows | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.syscounter
- vs.performance.property.wincounter
helpviewer_keywords:
- windows counters
- performance tools, using windows counters
- profiling tools, using windows counters
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 730345edb42ff3d14608bdcce91bc7b97c4bb478
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62973848"
---
# <a name="how-to-collect-windows-counter-data"></a>Postupy: Shromažďování dat čítačů Windows

Čítače Windows jsou systémové čítače výkonu, které mohou být shromážděných během profilace v nastavených intervalech. V zobrazení sestav nástrojů pro profilaci sady značek je označen řádek **AutoMark** pro každý interval shromažďování. Tento řádek obsahuje sloupce, které popisují hodnoty čítače výkonu v tomto intervalu. Chcete-li omezit analýzu na určitou dobu mezi dvěma konkrétními značkami, vyberte značky, klikněte pravým tlačítkem a pak vyberte **filtrovat podle** > **značky** z místní nabídky.

> [!NOTE]
> Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="to-collect-windows-counter-data"></a>Ke shromažďování dat čítačů Windows

1. V prohlížeči výkonu, klikněte pravým tlačítkem na relaci, pro kterou chcete konfigurovat čítače Windows a vyberte **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **čítače Windows**.

3. Vyberte **shromáždit čítače Windows** zaškrtávací políčko.

4. V **intervalem sběru hodnot (MS)** textové pole, zadejte časový interval.

5. Vybrat kategorii z **kategorie čítače** rozevíracího seznamu.

6. Vyberte instanci, ze **Instance** rozevíracího seznamu.

7. Vyberte čítače, které chcete použít při profilování aplikace.

8. Klikněte na tlačítko **použít.**

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
[vlastnosti relace výkonu](../profiling/performance-session-properties.md)
[čítače procesoru a Windows](../profiling/cpu-and-windows-counters.md)