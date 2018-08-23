---
title: Shromažďování dat souběžnosti procesu a vlákně | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
ms.assetid: fa03d381-a9ee-408c-876d-05111e29225b
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 935fbd89fa78ae7f05542eb0310f3e07673ee007
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669930"
---
# <a name="collecting-thread-and-process-concurrency-data"></a>Shromažďování dat o souběžnosti vláken a procesů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [shromažďování vlákna a dat o souběžnosti procesu](https://docs.microsoft.com/visualstudio/profiling/collecting-thread-and-process-concurrency-data).  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Metoda profilace souběžného zpracování nástrojů pro profilaci sady umožňuje shromažďovat data kolize prostředků, který obsahuje informace o každé synchronizaci událost, která způsobí, že funkce v profilované aplikace čekání na přístup k prostředku.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
 Můžete zadat souběžnosti metoda profilace pomocí jedné z následujících postupů:  
  
-   Klikněte na první stránce průvodce Profilováním, **souběžnosti**  
  
-   Na **Obecné** stránky dialogovém okně Vlastnosti relace výkonu můžete kliknout na tlačítko **souběžnosti**.  
  
-   Na **prohlížeč výkonu** nástrojů v **metoda** klikněte na možnost **souběžnosti**.  
  
## <a name="common-tasks"></a>Obecné úlohy  
 Můžete zadat další možnosti v *relace výkonu *** stránky vlastností** dialogovému oknu relace výkonu. Chcete-li otevřít toto dialogové okno:  
  
-   V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a potom klikněte na tlačítko **vlastnosti**.  
  
 Úkoly v následující tabulce popisují možnosti, které můžete určit *relace výkonu *** stránky vlastností** dialogové okno při profilování pomocí za použití metody souběžnosti.  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|Na **Obecné** stránce, pojmenování detailů generovaného souboru dat profilování (.vsp).|-   [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Na **spuštění** stránky, zadejte aplikaci spustit, pokud máte několik projektů .exe ve vašem kódu řešení.|-   [Postupy: určení binárního souboru ke spuštění](../profiling/how-to-specify-the-binary-to-start.md)|  
|Na **interakce vrstev** stránce, přidejte data pro volání ADO.NET pro spuštění profilování.|-   [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|  
|Na **čítače Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do profilových dat. jako značky.|-   [Postupy: shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|  
|Na **Upřesnit** stránky, zadejte verzi rozhraní .NET Framework doba běhu do profilu, pokud moduly vaše aplikace používat více verzí. Standardně je první verze načíst profilována.|-   [Postupy: určení modulu Runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|



