---
title: Zobrazení řádků | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.view.lines
helpviewer_keywords:
- profiling tools reports, Line view
- profiling tools, Line view
- Lines view
ms.assetid: 71ec0781-6031-4e17-af09-f50226018437
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dbfb1780cfb8a64ebe20fc45f02992e60d7bb201
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60049032"
---
# <a name="lines-view"></a>Zobrazení řádků
Zobrazení řádků je k dispozici pouze pro data profileru, která byla shromážděna pomocí metody vzorkování. Zobrazení není k dispozici pro data, která byla shromážděna pomocí instrumentace.

 Zobrazení řádků pro vzorkování dat profilu, identifikuje příkaz ve funkci, která byla spuštěna přímo po shromáždění vzorku. Zobrazení řádků pro data paměti .NET, identifikuje příkazy, které přidělují paměť.

 Ve zdrojovém souboru příkaz se týkají více než jeden řádek ve zdrojovém souboru a jeden řádek může obsahovat více než jeden výraz.

 Příkaz je identifikován následující:

- Zdrojový soubor, který obsahuje Function – příkaz

- Funkce, která obsahuje příkaz.

- Zdrojový řádek, ve kterém se spustí příkaz.

- Znak ve zdrojovém řádku, ve kterém se spustí příkaz.

- Řádku zdroje, u které končí příkaz.

- Znak ve zdrojovém řádku, kdy příkaz skončí.

## <a name="see-also"></a>Viz také:
- [Zobrazení řádků](../profiling/lines-view-sampling-data.md)
- [Zobrazení řádků – vzorkování](../profiling/lines-view-dotnet-memory-sampling-data.md)
- [Zobrazení řádků](../profiling/lines-view-contention-data.md)