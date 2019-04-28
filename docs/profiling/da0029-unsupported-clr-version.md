---
title: 'DA0029: Nepodporovaná verze CLR | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a3855b8975684b088b2838a866db36e6ec19e665
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62936285"
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: Nepodporovaná verze CLR

|||
|-|-|
|Id pravidla|DA0029|
|Kategorie|Použití nástroje pro profilaci|
|Metoda profilace|Profilace z příkazového řádku|
|Zpráva|Během shromažďování byla zjištěna nepodporovaná verze CLR. Nemůže vyřešit správně spravované symboly.|
|Typ pravidla|Informace.|

## <a name="cause"></a>Příčina
 Pokoušíte se profil aplikace, která se používá [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)] , která není podporována nástrojů pro profilaci.

## <a name="rule-description"></a>Popis pravidla
 K tomuto upozornění dochází, protože nástrojů pro profilaci, nebude možné vyřešit symboly pro spravovaný kód spuštěný v aplikaci. Nástroje pro profilaci nemůže vyřešit symboly spravovaného kódu pro aplikace, které jsou spuštěny [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)].

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Žádné