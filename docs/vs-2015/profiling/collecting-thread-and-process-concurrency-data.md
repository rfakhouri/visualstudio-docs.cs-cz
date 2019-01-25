---
title: Shromažďování dat souběžnosti procesu a vlákně | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
ms.assetid: fa03d381-a9ee-408c-876d-05111e29225b
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cf8a9de5f2a7e520a745fab81197016d6e1bd15d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54777009"
---
# <a name="collecting-thread-and-process-concurrency-data"></a>Shromažďování dat o souběžnosti vláken a procesů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Metoda profilace souběžného zpracování nástrojů pro profilaci sady umožňuje shromažďovat data kolize prostředků, který obsahuje informace o každé synchronizaci událost, která způsobí, že funkce v profilované aplikace čekání na přístup k prostředku.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
  Můžete zadat souběžnosti metoda profilace pomocí jedné z následujících postupů:  
  
- Klikněte na první stránce průvodce Profilováním, **souběžnosti**  
  
- Na **Obecné** stránky dialogovém okně Vlastnosti relace výkonu můžete kliknout na tlačítko **souběžnosti**.  
  
- Na **prohlížeč výkonu** nástrojů v **metoda** klikněte na možnost **souběžnosti**.  
  
## <a name="common-tasks"></a>Obecné úlohy  
 Můžete zadat další možnosti v _relace výkonu_**stránky vlastností** dialogovému oknu relace výkonu. Chcete-li otevřít toto dialogové okno:  
  
- V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a potom klikněte na tlačítko **vlastnosti**.  
  
  Úkoly v následující tabulce popisují možnosti, které můžete určit _relace výkonu_**stránky vlastností** dialogové okno při profilování pomocí za použití metody souběžnosti.  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|Na **Obecné** stránce, pojmenování detailů generovaného souboru dat profilování (.vsp).|-   [Jak: Nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Na **spuštění** stránky, zadejte aplikaci spustit, pokud máte několik projektů .exe ve vašem kódu řešení.|-   [Jak: Určení spouštěného binárního souboru](../profiling/how-to-specify-the-binary-to-start.md)|  
|Na **interakce vrstev** stránce, přidejte data pro volání ADO.NET pro spuštění profilování.|-   [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|  
|Na **čítače Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do profilových dat. jako značky.|-   [Jak: Shromažďování dat z čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|  
|Na **Upřesnit** stránky, zadejte verzi rozhraní .NET Framework doba běhu do profilu, pokud moduly vaše aplikace používat více verzí. Standardně je první verze načíst profilována.|-   [Jak: Určení modulu runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|
