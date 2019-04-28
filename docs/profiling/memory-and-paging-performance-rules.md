---
title: Pravidla výkonu paměti a stránkování | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1f779a050c334e8f61d6d3711ed2be2a7b087e72
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62896683"
---
# <a name="memory-and-paging-performance-rules"></a>Pravidla výkonu paměti a stránkování
Pravidla výkonu paměti a stránkování kategorie identifikovat stránkování během spuštění profilování, které můžou ovlivnit výkon aplikace a rychlost odezvy.

|||
|-|-|
|[DA0014: Velmi vysoké míry stránkování aktivní paměti na disk](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|K velmi vysokým mírám stránkování aktivní paměti na a z disku došlo k chybě během spuštění profilování. Stránkování sazby na této úrovni obvykle ovlivnit výkon aplikace a rychlost odezvy. Zvažte snížení přidělení paměti prostřednictvím revize algoritmy. Budete také muset zvážit požadavky na paměť vaší aplikace. Zkuste spustit profilaci znovu na počítači, který má více paměti. Toto pravidlo je vyvoláno, když objem stránkování překračuje prahovou hodnotu horní pravidla D0017.|
|[DA0017: Vysoké míry stránkování aktivní paměti na disk](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Relativně vysoké míry stránkování aktivní paměti na a z disku došlo k chybě během spuštění profilování. Stránkování sazby na této úrovni obvykle ovlivnit výkon aplikace a rychlost odezvy. Zvažte snížení přidělení paměti prostřednictvím revize algoritmy. Budete také muset zvážit požadavky na paměť vaší aplikace. Zkuste spustit profilaci znovu na počítači, který má více paměti.|