---
title: Shromažďování dat interakce vrstev | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.tierinteraction
helpviewer_keywords:
- Profiling Tools,ADO.NET profiling
- tier interaction profiling method
- Profiling Tools,tier-interaction method
- ADO.NET performance profiling
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 453dd2d93b8ac3c1a9ba2d194f20ee14897d6fa3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54918651"
---
# <a name="collect-tier-interaction-data"></a>Shromažďování dat interakce vrstev

Profilování interakce vrstev poskytuje další informace o spuštění s úspěšností funkce víceúrovňových aplikací, které komunikují s databázemi prostřednictvím služeb ADO.NET. Data se shromažďují pouze pro synchronní volání.

**Visual Studio editions**

Data profilace interakce vrstev lze shromažďovat pomocí libovolné edice sady Visual Studio. Nicméně data profilace interakce vrstev lze zobrazit pouze v sadě Visual Studio Enterprise.

**Windows 8 a Windows Server 2012**

Ke shromažďování dat interakce vrstev v aplikacích klasické pracovní plochy systému Windows 8 a Windows Server 2012 aplikace, musíte použít metody instrumentace. Nelze shromažďování dat interakce vrstev pro aplikace pro UPW. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md). Dat interakce vrstev můžete zahrnout všechny metody profilování na ostatní podporované verze systému Windows.

**Průvodce výkonu**

Z důvodu chyby v Průvodci výkonu je nutné přidat možnost kolekce dat interakce vrstvy do běhu profilování z prohlížeče výkonu. Musíte také přidat projekt, spustitelný soubor nebo web na cílový uzel prohlížeč výkonu.

## <a name="to-add-tier-interaction-data-to-a-profiling-run-by-using-the-performance-session-property-pages"></a>Přidání dat interakce vrstev pro profilování pomocí stránky vlastností relace výkonu

1. V Průzkumníku výkonu, zvolte **vlastnosti** v místní nabídce.

2. Vyberte **interakce vrstev** stránce a potom zkontrolujte **povolit profilaci interakce vrstev** zaškrtávací políčko.

3. V prohlížeči výkonu, vyberte **cíle** uzel a pak zadejte projekt, spustitelný soubor nebo web, který chcete Profilovat.

## <a name="see-also"></a>Viz také:

[Zobrazení interakcí vrstev](../profiling/tier-interactions-view.md)