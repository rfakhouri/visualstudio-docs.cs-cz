---
title: 'Postupy: Shromažďování trasování událostí pro Windows (ETW) Data | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.events
helpviewer_keywords:
- event trace providers, performance tools
- profiling tools, event trace providers
- performance tools, enabling event trace providers
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d9734c75f078380649009d10da13ed8c926e5e16
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62973861"
---
# <a name="how-to-collect-event-tracing-for-windows-etw-data"></a>Postupy: Shromažďování dat trasování událostí pro Windows (ETW)

Event Tracing for Windows (ETW) je efektivní sledování na úrovni jádra zařízení, která umožňuje profileru jádra protokolu nebo události definované aplikací. Data, která se shromažďují ze zprostředkovatele událostí může zobrazit pouze pomocí /**Summary: ETW** možnost [VSPerfReport](../profiling/vsperfreport.md) nástroj příkazového řádku. Tato sestava slouží k určení, kdy dojde k problémům s výkonem v aplikaci.

> [!NOTE]
> Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="to-enable-event-trace-providers"></a>Povolení zprostředkovatelé trasování událostí

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na relaci výkonu a pak klikněte na tlačítko **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **události Windows** vlastnosti.

3. V **vyberte poskytovatel trasování pro shromažďování dat z** vyberte zprostředkovatele událostí, které chcete použít pro profilování aplikace.

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)