---
title: Shromažďování dat souběžnosti procesu a vlákně | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2c3310a87a4b25e560ea5303553e3eb75c0da001
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56603609"
---
# <a name="collect-thread-and-process-concurrency-data"></a>Shromažďování dat o souběžnosti vláken a procesů

Metoda profilace souběžného zpracování profilování nástroje sady Visual Studio umožňuje shromažďovat data kolize prostředků, který obsahuje informace o každé synchronizaci událost, která způsobí, že funkce v profilované aplikace čekání na přístup k prostředku.

Můžete zadat souběžnosti metoda profilace pomocí jedné z následujících postupů:

- Klikněte na první stránce průvodce Profilováním, **souběžnosti**
- Na **Obecné** stránky dialogovém okně Vlastnosti relace výkonu můžete kliknout na tlačítko **souběžnosti**.
- Na **prohlížeč výkonu** nástrojů v **metoda** klikněte na možnost **souběžnosti**.

## <a name="common-tasks"></a>Běžné úkoly

Můžete zadat další možnosti v _relace výkonu_**stránky vlastností** dialogovému oknu relace výkonu. Chcete-li otevřít toto dialogové okno:

- V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a potom klikněte na tlačítko **vlastnosti**.

Úkoly v následující tabulce popisují možnosti, které můžete určit _relace výkonu_**stránky vlastností** dialogové okno při profilování pomocí za použití metody souběžnosti.

|Úloha|Související obsah|
|----------|---------------------|
|Na **Obecné** stránce, pojmenování detailů generovaného souboru dat profilování (.vsp).|- [Jak: Nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|
|Na **spuštění** stránky, zadejte aplikaci spustit, pokud máte několik projektů .exe ve vašem kódu řešení.|- [Jak: Určení binárního souboru ke spuštění](../profiling/how-to-specify-the-binary-to-start.md)|
|Na **interakce vrstev** stránce, přidejte data pro volání ADO.NET pro spuštění profilování.|- [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|
|Na **čítače Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do profilových dat. jako značky.|- [Jak: Shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|
|Na **Upřesnit** stránky, zadejte verzi rozhraní .NET Framework doba běhu do profilu, pokud moduly vaše aplikace používat více verzí. Standardně je první verze načíst profilována.|- [Jak: Určení modulu runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|