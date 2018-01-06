---
title: "Řešení potíží s výkonem nástroje problémy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b61cdf7-75b7-4abd-aff2-7bd997717626
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 748f642e4bd150c8ec5819057b4ee3f7768893f0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-performance-tools-issues"></a>Řešení potíží s výkonem nástroje problémy
Při použití nástroje pro profilaci setkat s jedním z následujících problémů:  
  
-   [Žádná Data se shromažďují nástroje pro profilaci](#NoDataCollected)  
  
-   [Zobrazení výkonu a zobrazení čísel sestavy pro názvy funkcí](#NoSymbols)  
  
##  <a name="NoDataCollected"></a>Žádná Data se shromažďují nástroje pro profilaci  
 Po profil aplikace nevytvoří soubor profilování dat (.vsp) a v okně výstupu nebo v příkazovém okně se zobrazí následující upozornění:  
  
 PRF0025: Nebyla shromážděna žádná data.  
  
 Tento problém může být způsobeno několika problémy:  
  
-   Proces, který byl vytvořený profil s použitím vzorkuje nebo metodu paměti .NET spustí podřízený proces, který změní proces, který provede práci aplikace. Například některé aplikace číst příkazového řádku k určení, zda byly spuštěny jako aplikace systému Windows nebo jako aplikace příkazového řádku. Pokud se vyžaduje aplikace systému Windows, proces původní spustí nový proces nakonfigurovaný jako aplikace pro systém Windows a pak původní proces bude ukončen. Protože nástrojích pro profilaci neshromažďují automaticky data pro podřízené procesy, je nebyla shromážděna žádná data.  
  
     Chcete-li shromažďovat data profilování v této situaci, připojení profileru k podřízeného procesu místo spouštění aplikace s profilerem. Další informace najdete v tématu [postupy: připojení a odpojení nástroje pro sledování výkonu pro procesy spuštění](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md) a [připojit (VSPerfCmd)](../profiling/attach.md)  
  
##  <a name="NoSymbols"></a>Zobrazení výkonu a zobrazení čísel sestavy pro názvy funkcí  
 Po profil aplikace zobrazí čísla namísto názvů funkce v zobrazení a sestavy.  
  
 Tento problém je způsoben modulu analýzy nástrojích pro profilaci se nepodařilo najít soubory PDB, které obsahují informace symbol, který se mapuje na zkompilovaný soubor zdrojového kódu informace, tyto názvy funkcí a čísla řádků. Ve výchozím nastavení vytvoří kompilátor na soubor .pdb při vytváření souboru aplikace. Odkaz na místním adresáři na soubor .pdb ukládána kompilované aplikace. Analytický modul vypadá v odkazované adresáře pro soubor .pdb a pak v souboru, který aktuálně obsahuje souboru aplikace. Pokud není nalezen soubor .pdb, modul analysis posuny funkce používá namísto názvů funkce.  
  
 Tento problém mohli vyřešit v jednom ze dvou způsobů:  
  
-   Najít soubory PDB a umístěte je do stejného adresáře jako soubory aplikace.  
  
-   Vložení informací o symbolu v profilaci souboru dat (.vsp). Další informace najdete v tématu [ukládání informací o symbolech s datovými soubory výkonu](../profiling/saving-symbol-information-with-performance-data-files.md).  
  
> [!NOTE]
>  Analytický modul vyžaduje, aby na soubor .pdb stejnou verzi jako soubor kompilované aplikace. Soubor .pdb ze dřívější nebo novější sestavení souboru aplikace nebude fungovat.