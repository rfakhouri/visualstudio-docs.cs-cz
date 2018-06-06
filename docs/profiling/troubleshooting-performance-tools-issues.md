---
title: Řešení potíží s výkonem nástroje problémy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 0b61cdf7-75b7-4abd-aff2-7bd997717626
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db48b940fecb27dd4f41b5fc56f32ee2cc4f5f02
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572342"
---
# <a name="troubleshoot-performance-tools-issues"></a>Řešení potíží s výkonem nástroje
Při použití nástroje pro profilaci setkat s jedním z následujících problémů:  
  
-   [Žádná data se shromažďují pomocí nástrojů pro profilaci](#NoDataCollected)  
  
-   [Zobrazení a sestavách výkonu zobrazení čísel pro názvy – funkce](#NoSymbols)  
  
## <a name="no-data-is-collected-by-the-profiling-tools"></a>Žádná data se shromažďují pomocí nástrojů pro profilaci  
 Po profilu aplikace, data profilování (. *Vsp*) soubor není vytvořen a zobrazí se následující upozornění v **výstup** okno nebo v příkazovém okně:  
  
 PRF0025: Nebyla shromážděna žádná data.  
  
 Tento problém může být způsobeno několika problémy:  
  
-   Proces, který byl vytvořený profil s použitím vzorkuje nebo metodu paměti .NET spustí podřízený proces, který změní proces, který provede práci aplikace. Například některé aplikace číst příkazového řádku k určení, zda byly spuštěny jako aplikace systému Windows nebo jako aplikace příkazového řádku. Pokud se vyžaduje aplikace systému Windows, proces původní spustí nový proces nakonfigurovaný jako aplikace pro systém Windows a pak původní proces bude ukončen. Protože nástrojích pro profilaci neshromažďují automaticky data pro podřízené procesy, je nebyla shromážděna žádná data.  
  
     Chcete-li shromažďovat data profilování v této situaci, připojení profileru k podřízeného procesu místo spouštění aplikace s profilerem. Další informace najdete v tématu [postupy: připojení a odpojení nástroje pro sledování výkonu ke spuštěným procesům](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md) a [připojit (VSPerfCmd)](../profiling/attach.md)  
  
## <a name="performance-views-and-reports-display-numbers-for-function-names"></a>Zobrazení a sestavách výkonu zobrazení čísel pro názvy – funkce  
 Po profil aplikace zobrazí čísla namísto názvů funkce v zobrazení a sestavy.  
  
 Tento problém je způsoben modulu nástrojích pro profilaci analýzy, není schopen najít. *pdb* soubory, které obsahují informace o symbolu, mapy zdrojového kódu informace, tyto názvy funkcí a čísla řádků do kompilované souboru. Ve výchozím nastavení, kompilátor vytvoří. *pdb* souboru při vytváření souboru aplikace. Odkaz na místní adresáře. *pdb* kompilované aplikace je uložený soubor. Analytický modul hledá v adresáři odkazované pro. *pdb* souboru a potom v souboru aktuálně obsahující souboru aplikace. Pokud. *pdb* soubor nebyl nalezen, modul analysis posuny funkce používá namísto názvů funkce.  
  
 Tento problém mohli vyřešit v jednom ze dvou způsobů:  
  
-   Najít. *pdb* soubory a umístěte je do stejného adresáře jako soubory aplikace.  
  
-   Vložení informací o symbolu v profilaci data (. *Vsp*) souboru. Další informace najdete v tématu [uložení informací o symbolech s výkonem datové soubory](../profiling/saving-symbol-information-with-performance-data-files.md).  
  
> [!NOTE]
>  Analytický modul vyžaduje, aby. *pdb* souboru se stejnou verzi jako soubor kompilované aplikace. A. *pdb* soubor z sestavení starší nebo novější souboru aplikace nebude fungovat.