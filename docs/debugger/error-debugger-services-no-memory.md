---
title: Ladicí program služby nemá dostatek paměti | Dokumentace Microsoftu
ms.date: 07/10/2019
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.debug_no_memory
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger
author: isadorasophia
ms.author: isgarcia
manager: caslan
ms.workload:
- multiple
ms.openlocfilehash: 05664ffd056f69215e6fb00d6d49a59382a3692f
ms.sourcegitcommit: da4079f5b6ec884baf3108cbd0519d20cb64c70b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861171"
---
# <a name="debugger-services-running-out-of-memory"></a>Ladicí program služby nemá dostatek paměti
Ladění služby není dostatek paměti a způsobila ukončení relace ladění.

## <a name="to-investigate-this-error-on-windows"></a>K prozkoumání této chybě ve Windows
- Graf paměti procesu můžete zkontrolovat **diagnostické nástroje** okno a zobrazit, pokud je cílová aplikace dochází k velký nárůst v paměti. Pokud ano, použít **využití paměti** nástroj pro diagnostiku, co je daný problém, naleznete v tématu [analýza využití paměti](../profiling/memory-usage.md).

- Pokud je cílová aplikace nefunguje by spotřebovávalo velké množství paměti, použijte **Správce úloh** okno a podívejte se na využití paměti sady Visual Studio (devenv.exe), pracovním procesem (msvsmon.exe), nebo VS Code (vsdbg.exe/vsdbg-ui.exe) Určete, pokud se jedná o problém ladicího programu. Pokud proces, který běží mimo paměť je devenv.exe, zvažte snížení počtu rozšíření sady Visual Studio spuštěná.

## <a name="see-also"></a>Viz také
- [Blogový příspěvek: Analýza využití procesoru a paměti během ladění](https://devblogs.microsoft.com/visualstudio/analyze-cpu-memory-while-debugging/)
- [Správa paměti](/windows/win32/memory/about-memory-management)
