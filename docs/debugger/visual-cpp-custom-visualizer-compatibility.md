---
title: Kompatibilita Visual C/C++ vlastní vizualizér
ms.date: 01/28/2019
ms.prod: visual-studio-dev16
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging assertions
- assertions, debugging
- assertions, assertion failures
- Assertion Failed dialog box
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.openlocfilehash: 32e38dd3bba8a1127d8756972b73e8b47a514f1b
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335178"
---
# <a name="visual-cc-custom-visualizer-compatibility"></a>Kompatibilita Visual C/C++ vlastní vizualizér

Od verze Visual Studio 2019, Visual C++ obsahuje vylepšené ladicí program, který používá externí 64bitový proces pro hostování součásti vysokými nároky na paměť. V rámci této aktualizace se určitá rozšíření pro vyhodnocovací filtr výrazů jazyka Visual C/C++ se musí aktualizovat tak, aby byly kompatibilní s novou ladicího programu.

Pokud jsou aktuálně spotřebovává starší verze jazyka C/C++ EE doplněk nebo vlastní vizualizér C/C++, můžete vypnout používání tohoto externího procesu tak, že přejdete do **nástroje** > **možnosti**  >   **Ladění**a následně zrušením výběru **zatížení ladicí symboly v externím procesu (pouze nativní)**. Pokud výběr této možnosti dojde k významné zvýšení využití paměti v rámci procesu integrovaného vývojového prostředí (devenv.exe). Ano Pokud očekáváte, chcete-li ladit velké projekty, se doporučuje pracovat s vlastníkem rozšíření, aby byl kompatibilní s touto možností ladění.

Pokud jste vlastníkem starší verze jazyka C/C++ EE doplněk nebo vlastní vizualizér C/C++, najdete další informace o výběru načítající vaše rozšíření v pracovním procesu na [ukázky rozšiřitelnosti Concord wiki](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Worker-Process-Remoting). Můžete také vyhledat [ukázky jazyka C/C++ vlastní vizualizér](https://github.com/Microsoft/ConcordExtensibilitySamples/tree/master/CppCustomVisualizer).