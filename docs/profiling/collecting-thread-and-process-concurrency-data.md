---
title: Shromažďování dat souběžnosti proces a vlákno | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 424675726dd91664923cde0a3a5ad5573d51b4d5
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
---
# <a name="collect-thread-and-process-concurrency-data"></a>Shromažďování dat souběžnosti vláken a procesů

Metoda profilace souběžného zpracování profilace nástroje sady Visual Studio umožňuje shromažďování dat kolizí prostředku, který obsahuje informace o každé synchronizace událost, která způsobí, že funkci v aplikaci PROFILOVANÉHO čekání na přístup k prostředku.

Můžete určit souběžnosti metoda profilace pomocí jedné z následujících postupů:

- Na první stránce průvodce profilace, klikněte na tlačítko **souběžnosti**
- Na **Obecné** stránky dialogovém okně Vlastnosti výkonnostní relace klikněte na tlačítko **souběžnosti**.
- Na **prohlížeč výkonu** panelu nástrojů v **metoda** seznamu, klikněte na tlačítko **souběžnosti**.

## <a name="common-tasks"></a>Běžné úlohy

Můžete zadat další možnosti v *výkonnostní relace *** stránky vlastností** dialogové okno relace výkonu. Chcete-li otevřít toto dialogové okno:

- V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a pak klikněte na tlačítko **vlastnosti**.

Úkoly v následující tabulce popisují možnosti, které můžete zadat v *výkonnostní relace *** stránky vlastností** dialogové okno když profilu pomocí metody souběžnosti.

|Úloha|Související obsah|
|----------|---------------------|
|Na **Obecné** zadejte pojmenování podrobnosti vygenerovaný soubor profilování dat (.vsp).|- [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|
|Na **spustit** stránky, zadejte aplikaci spustit, pokud máte více .exe projekty v řešení pro kód.|- [Postupy: určení binárního souboru ke spuštění](../profiling/how-to-specify-the-binary-to-start.md)|
|Na **sledováním interakce vrstev** přidejte ADO.NET data volání do profilace spustit.|- [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|
|Na **čítačů systému Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do data profilování jako značky.|- [Postupy: shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|
|Na **Upřesnit** určete verzi běhové rozhraní .NET Framework profil, pokud vaše aplikace moduly pomocí více verzí. Ve výchozím nastavení je první verze načíst profilovaným.|- [Postupy: Zadejte modul runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|