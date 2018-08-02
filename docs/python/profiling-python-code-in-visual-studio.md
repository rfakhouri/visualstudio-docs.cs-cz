---
title: Měření výkonu kódu Python
description: Jak používat kód profileru sady Visual Studio zkontrolovat výkon Pythonu při interpretů usnig na základě CPython.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: feafc7d53e8d450bc980b6d842e9c2a5f0ade2e4
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468813"
---
# <a name="profile-python-code"></a>Profil kódu Pythonu

Při použití na základě CPython interpretů můžete provádět profilaci aplikace v Pythonu. (Viz [matice funkcí – profilace](overview-of-python-tools-for-visual-studio.md#matrix-profiling) této funkce pro různé verze sady Visual Studio je k dispozici.)

## <a name="profiling-for-cpython-based-interpreters"></a>Profilace pro na základě CPython interpretery

Profilace je spuštěn prostřednictvím **analyzovat** > **spuštění profilování Pythonu** příkaz nabídky, které se otevře dialogové okno konfigurace:

![Dialogové okno Konfigurace profilace](media/profiling-start.png)

Když vyberete **OK**, profiler běží a otevře se sestava výkonu, pomocí kterého můžete prozkoumat, jak je čas strávený v aplikaci:

![Sestava profilace výkonu](media/profiling-results.png)

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | [Podívejte se na video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567) ukázku pythonu profilace (3 m 00s).|

> [!Note]
> V současné době Visual Studio podporuje pouze tuto úroveň profilace celé aplikace, ale určitě chceme slyšet váš názor na budoucí funkce. Použití [ **poskytnout názor na produkt** tlačítko](#feedback) v dolní části této stránky.

## <a name="profiling-for-ironpython"></a>Profilace pro IronPython

Protože IronPython není překladač na základě CPython, výše uvedené funkce profilování nebude fungovat.

Místo toho použijte profiler sady Visual Studio .NET spuštěním *ipy.exe* přímo jako cílovou aplikaci, pomocí příslušnými argumenty pro spuštění spouštěcího skriptu. Zahrnout `-X:Debug` na příkazový řádek pro zajištění, že všechna vaše Python kód ladit a Profilovat. Tento argument generuje sestavu výkonu včetně času stráveného v modulu runtime IronPython a váš kód. Váš kód je identifikován pomocí pozměnění názvy.

Alternativně Ironpythonu má některé vlastní integrované profilování, ale aktuálně nejsou k dispozici žádné vhodné vizualizér pro něj. Zobrazit [Profiler IronPython](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx) (Blogy MSDN) pro co je k dispozici.