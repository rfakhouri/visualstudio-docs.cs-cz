---
title: Řešení potíží s výkonem problémy s nástroji | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: troubleshooting
ms.assetid: 0b61cdf7-75b7-4abd-aff2-7bd997717626
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 575f17c641eb057dc01fb3302098bd9f8b47f9c5
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431614"
---
# <a name="troubleshooting-performance-tools-issues"></a>Řešení potíží s výkonem problémy s nástroji
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při použití nástrojů pro profilaci setkat s jedním z následujících problémů:  
  
- [Nebyla shromážděna žádná Data je pomocí nástrojů pro profilaci](#NoDataCollected)  
  
- [Zobrazení výkonu a sestavy zobrazit čísla pro názvy – funkce](#NoSymbols)  
  
## <a name="NoDataCollected"></a> Nebyla shromážděna žádná Data je pomocí nástrojů pro profilaci  
 Poté, co Profilovat aplikaci není vytvořena souboru dat profilování (.vsp) a v okně výstupu nebo v příkazovém okně se zobrazí následující upozornění:  
  
 PRF0025: Nebyla shromážděna žádná data.  
  
 Tento problém může být způsobeno několika problémy:  
  
- Proces, který profilované za použití vzorkování nebo metoda paměti .NET spustí podřízený proces, který je proces, který provádí aplikace. Například některé aplikace číst příkazový řádek pro zjištění, zda bylo zahájeno jako aplikace Windows nebo jako aplikace příkazového řádku. Pokud o to požádá o aplikaci Windows se spustí nový proces, který je nakonfigurován jako aplikace Windows se původní proces a následně původní proces skončí. Protože nástrojů pro profilaci nejsou shromažďovány automaticky data pro podřízené procesy, je nebyla shromážděna žádná data.  
  
     Ke shromažďování dat profilace v této situaci, připojení profileru k podřízenému procesu namísto spuštění aplikace s profilerem. Další informace najdete v tématu [jak: Připojení a odpojení nástroje Sledování výkonu ke spuštěným procesům](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md) a [připojit (VSPerfCmd)](../profiling/attach.md)  
  
## <a name="NoSymbols"></a> Zobrazení výkonu a sestavy zobrazit čísla pro názvy – funkce  
 Poté, co Profilovat aplikaci zobrazit čísla namísto názvy funkcí v sestavách a zobrazení.  
  
 Tento problém je způsoben analytický modul nástrojů pro profilaci sady se nepodařilo najít soubory s příponou .pdb, které obsahují informace o symbolu, který se mapuje zkompilovaný soubor informací o zdrojovém kódu, tyto názvy funkcí a čísla řádků. Ve výchozím nastavení kompilátor vytvoří soubor PDB při vytváření souboru aplikace. Odkaz na místní adresář souboru PDB je uložen v kompilované aplikaci. V modulu analýzy vypadá v odkazované adresář pro soubor typu .pdb a pak v souboru, který aktuálně obsahuje soubor aplikace. Pokud se nenajde soubor typu .pdb, používá modul analýzy posunů funkce místo názvy funkcí.  
  
 Problém můžete vyřešit jedním ze dvou způsobů:  
  
- Najít soubory s příponou .pdb a umístit je do stejného adresáře jako soubory aplikace.  
  
- Vložte informace symbolu souboru dat profilování (.vsp). Další informace najdete v tématu [ukládání informací o symbolech s datových souborů výkonu](../profiling/saving-symbol-information-with-performance-data-files.md).  
  
> [!NOTE]
> Analytický modul vyžaduje, aby soubor typu .pdb stejnou verzi jako soubor kompilované aplikace. Soubor PDB z dřívější nebo pozdější sestavování souboru aplikace nebude fungovat.
