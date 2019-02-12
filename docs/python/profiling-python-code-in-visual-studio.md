---
title: Měřit výkon kódu v Pythonu
description: Zkontrolovat výkon kódu Pythonu při použití na základě CPython interpretů pomocí profileru sady Visual Studio.
ms.date: 11/12/2018
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 985b0120d54cf7a606bcf2bab5b11ae416d986a3
ms.sourcegitcommit: 34940a18f5b03a59567f54c7024a0b16d4272f1e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/12/2019
ms.locfileid: "56155133"
---
# <a name="profile-python-code"></a>Profil kódu Pythonu

Při použití na základě CPython interpretů můžete provádět profilaci aplikace v Pythonu. (Viz [matice funkcí – profilace](overview-of-python-tools-for-visual-studio.md#matrix-profiling) této funkce pro různé verze sady Visual Studio je k dispozici.)

## <a name="profiling-for-cpython-based-interpreters"></a>Profilace pro na základě CPython interpretery

Profilace je spuštěn prostřednictvím **analyzovat** > **spuštění profilování Pythonu** příkaz nabídky, které se otevře dialogové okno konfigurace:

![Dialogové okno Konfigurace profilace](media/profiling-start.png)

Když vyberete **OK**, profiler běží a otevře se sestava výkonu, pomocí kterého můžete prozkoumat, jak je čas strávený v aplikaci:

![Sestava profilace výkonu](media/profiling-results.png)

> [!Note]
> V současné době Visual Studio podporuje pouze tuto úroveň profilace celé aplikace, ale určitě chceme slyšet váš názor na budoucí funkce. Použití [ **názor na produkt** tlačítko](#feedback) v dolní části této stránky.

## <a name="profiling-for-ironpython"></a>Profilace pro IronPython

Protože IronPython není překladač na základě CPython, výše uvedené funkce profilování nebude fungovat.

Místo toho použijte profiler sady Visual Studio .NET spuštěním *ipy.exe* přímo jako cílovou aplikaci, pomocí příslušnými argumenty pro spuštění spouštěcího skriptu. Zahrnout `-X:Debug` na příkazový řádek pro zajištění, že všechna vaše Python kód ladit a Profilovat. Tento argument generuje sestavu výkonu včetně času stráveného v modulu runtime IronPython a váš kód. Váš kód je identifikován pomocí pozměnění názvy.

Alternativně Ironpythonu má některé vlastní integrované profilování, ale aktuálně nejsou k dispozici žádné vhodné vizualizér pro něj. Zobrazit [Profiler IronPython](https://blogs.msdn.microsoft.com/curth/2009/03/30/an-ironpython-profiler/) (Blogy MSDN) pro co je k dispozici.
