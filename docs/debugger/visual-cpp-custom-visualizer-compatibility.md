---
title: Kompatibilita Visual C/C++ vlastní vizualizér
ms.date: 01/28/2019
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging assertions
- assertions, debugging
- assertions, assertion failures
- Assertion Failed dialog box
ms.assetid: 64af5bed-e38b-420f-b9ce-d64f35100aae
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.openlocfilehash: 3c90c66e338330d77af29564c7586e68b8ee35b6
ms.sourcegitcommit: 01334abf36d7e0774329050d34b3a819979c95a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55852605"
---
# <a name="visual-cc-custom-visualizer-compatibility"></a>Kompatibilita Visual C/C++ vlastní vizualizér

Od verze Visual Studio 2019, Visual C++ obsahuje vylepšené ladicí program, který používá externí 64bitový proces pro hostování součásti vysokými nároky na paměť. V rámci této aktualizace se určitá rozšíření pro vyhodnocovací filtr výrazů jazyka Visual C/C++ se musí aktualizovat tak, aby byly kompatibilní s novou ladicího programu.

Pokud jsou aktuálně spotřebovává starší verze jazyka C/C++ EE doplněk nebo vlastní vizualizér C/C++, můžete vypnout používání tohoto externího procesu tak, že přejdete do **nástroje** > **možnosti**  >   **Ladění**a následně zrušením výběru **zatížení ladicí symboly v externím procesu (pouze nativní)**. Pokud výběr této možnosti dojde k významné zvýšení využití paměti v rámci procesu integrovaného vývojového prostředí (devenv.exe). Ano Pokud očekáváte, chcete-li ladit velké projekty, se doporučuje pracovat s vlastníkem rozšíření, aby byl kompatibilní s touto možností ladění.

Pokud jste vlastníkem starší verze jazyka C/C++ EE doplněk nebo vlastní vizualizér C/C++, najdete další informace o výběru načítající vaše rozšíření v pracovním procesu na [ukázky rozšiřitelnosti Concord wiki](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Worker-Process-Remoting). Můžete také vyhledat [ukázky jazyka C/C++ vlastní vizualizér](https://github.com/Microsoft/ConcordExtensibilitySamples/tree/master/CppCustomVisualizer).