---
title: Řešení potíží s výkonem problémy s nástroji | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0b61cdf7-75b7-4abd-aff2-7bd997717626
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ef65019223ba1978ea31fbdb9020993a166da89b
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63422202"
---
# <a name="troubleshoot-performance-tools-issues"></a>Řešení problémů s výkonem nástroje
Při použití nástrojů pro profilaci setkat s jedním z následujících problémů:

- [Nebyla shromážděna žádná data je pomocí nástrojů pro profilaci](#no-data-is-collected-by-the-profiling-tools)

- [Zobrazení výkonu a sestavy zobrazit čísla pro názvy – funkce](#performance-views-and-reports-display-numbers-for-function-names)

## <a name="no-data-is-collected-by-the-profiling-tools"></a>Nebyla shromážděna žádná data je pomocí nástrojů pro profilaci
 Poté, co Profilovat aplikaci dat profilování (. *Vsp*) se vytvoří soubor a zobrazí se následující upozornění v **výstup** okna nebo v příkazovém okně:

 PRF0025: Nebyla shromážděna žádná data.

 Tento problém může být způsobeno několika problémy:

- Proces, který profilované za použití vzorkování nebo metoda paměti .NET spustí podřízený proces, který je proces, který provádí aplikace. Například některé aplikace číst příkazový řádek pro zjištění, zda bylo zahájeno jako aplikace Windows nebo jako aplikace příkazového řádku. Pokud o to požádá o aplikaci Windows se spustí nový proces, který je nakonfigurován jako aplikace Windows se původní proces a následně původní proces skončí. Protože nástrojů pro profilaci nejsou shromažďovány automaticky data pro podřízené procesy, je nebyla shromážděna žádná data.

     Ke shromažďování dat profilace v této situaci, připojení profileru k podřízenému procesu namísto spuštění aplikace s profilerem. Další informace najdete v tématu [jak: Připojení a odpojení nástroje Sledování výkonu ke spuštěným procesům](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md) a [připojit (VSPerfCmd)](../profiling/attach.md)

## <a name="performance-views-and-reports-display-numbers-for-function-names"></a>Zobrazení výkonu a sestavy zobrazit čísla pro názvy – funkce
 Poté, co Profilovat aplikaci zobrazit čísla namísto názvy funkcí v sestavách a zobrazení.

 Tento problém je způsoben není schopen najít v modulu analýzy nástroje pro profilaci. *pdb* soubory, které obsahují informace o symbolech, že mapování zdroje informací o kódu, tyto názvy funkcí a čísla řádků do kompilovaného souboru. Ve výchozím nastavení, kompilátor vytvoří. *pdb* soubor při vytváření souboru aplikace. Odkaz na místní adresář. *pdb* soubor je uložen v kompilované aplikace. V modulu analýzy hledá v odkazované v adresáři. *pdb* souboru a potom v souboru, který aktuálně obsahuje soubor aplikace. Pokud. *pdb* nenašel se soubor, používá modul analýzy posunů funkce místo názvy funkcí.

 Problém můžete vyřešit jedním ze dvou způsobů:

- Najít. *pdb* soubory a umístit je do stejného adresáře jako soubory aplikace.

- Vložení informací o symbolu dat profilování (. *Vsp*) soubor. Další informace najdete v tématu [uložit informace o symbolech s výkonem datové soubory](../profiling/saving-symbol-information-with-performance-data-files.md).

> [!NOTE]
> Analytický modul vyžaduje, aby. *pdb* soubor má stejnou verzi jako soubor kompilované aplikace. ODPOVĚĎ. *pdb* soubor z dřívější nebo pozdější sestavování souboru aplikace nebude fungovat.