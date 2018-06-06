---
title: 'Postupy: shromažďování dat čítačů Windows | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a68ed7789e1f77e6bd130ff29bcbb82700f3507
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34814902"
---
# <a name="how-to-collect-windows-counter-data"></a>Postupy: shromažďování dat čítačů Windows

Čítače systému Windows jsou čítače výkonu systému, které se můžou shromažďovat ve stanovených intervalech při vytváření profilu. V zobrazení značky sestavy nástrojích pro profilaci řádek označený **pro automatické označování** v každém intervalu kolekce. Řádek obsahuje sloupce, které popisují hodnoty čítače výkonu v tomto intervalu. Analýza omezit na určitou dobu mezi dvěma konkrétní značky, vyberte značky, klikněte pravým tlačítkem a pak vyberte **filtrovat podle**>**značky** z místní nabídky.

> [!NOTE]
> Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="to-collect-windows-counter-data"></a>Chcete-li shromažďování dat čítačů Windows

1. V Průzkumníku výkonu, klikněte pravým tlačítkem na relaci, pro který chcete konfigurovat čítačů systému Windows a vyberte **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **čítačů systému Windows**.

3. Vyberte **shromažďování čítačů systému Windows** zaškrtávací políčko.

4. V **interval sběru (MS)** textové pole, zadejte časový interval.

5. Vyberte kategorii z **kategorie čítače** rozevíracího seznamu.

6. Vyberte instanci z **Instance** rozevíracího seznamu.

7. Vyberte čítače, které chcete použít při profil aplikace.

8. Klikněte na tlačítko **použít.**

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)  
[Čítače procesoru a systému Windows](../profiling/cpu-and-windows-counters.md)