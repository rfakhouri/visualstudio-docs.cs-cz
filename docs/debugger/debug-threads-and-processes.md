---
title: Nástroje pro ladění vláken a procesů | Microsoft Docs
ms.custom: ''
ms.date: 04/21/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multiprocess debugging
- threading [Visual Studio], debugging
- processes, debugging
- debugging threads
- debugging [Visual Studio], threads
ms.assetid: 9f0c8505-b6b2-452b-adfd-076db14d8115
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f92a0497ebdf8fdfec03dd6a37aac8238517e0e1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="tools-to-debug-threads-and-processes-in-visual-studio"></a>Nástroje pro ladění vláken a procesů v sadě Visual Studio
*Vlákna* a *procesy* jsou související koncepty v počítači vědecké účely. Obě představují pořadí pokyny, které musí být spuštěn v určitém pořadí. Pokyny v samostatných vláknech a procesy, ale můžete paralelně spustit.  
  
 Procesy existovat v operačním systému a odpovídají co uživatelé uvidí jako programy nebo aplikace. Vlákno, na druhé straně existuje v rámci procesu. Z tohoto důvodu vláken se někdy označují jako *šedé – procesy*. Každý proces se skládá z jednoho nebo více vláken.  
  
 Existenci více procesů umožňuje počítači provádět více než jeden úkol najednou. Existenci více vláken umožňuje proces pro jednotlivé pracovní mají být provedeny souběžně. Na počítači s více procesory procesů nebo vláken můžete spustit na různé procesory. To umožňuje true paralelní zpracování.  
  
 Ideální paralelní zpracování vždy není možné. Vlákna někdy musí být synchronizovány. Jedno vlákno pravděpodobně nutné čekat na výsledek z jiné vlákno nebo jedno vlákno může být nutné výhradní přístup k prostředku, který používá jiné vlákno. Synchronizace problémy jsou obvyklou příčinou chyby v vícevláknové aplikace. Vlákna někdy může stát čekání na prostředek, který nikdy bude k dispozici. Výsledek v podmínce názvem *zablokování*.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ladicí program poskytuje výkonné, ale snadné použití nástroje pro ladění vláken a procesů.  
  
## <a name="tools-and-features"></a>Nástroje a funkce
Nástroje, které potřebujete pro použití v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] závisí na jaký typ kódu se pokoušíte ladění:

- U procesů, jsou mezi primární nástroje **připojit k procesu** dialogové okno, **procesy** okně a **ladění umístění** panelu nástrojů.

- Pro vlákna, jsou mezi primární nástroje k ladění vláken **vláken** okno, značek přístup z více vláken ve windows zdroj **paralelní zásobníky** okně **paralelního sledování** okně a **ladění umístění** panelu nástrojů.  
  
- Pro kód, který používá <xref:System.Threading.Tasks.Task> v [Task Parallel Library (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl), [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime/) (nativního kódu), mezi primární nástroje pro ladění vícevláknové aplikace jsou **Paralelní zásobníky** okně **paralelního sledování** okně a **úlohy** okno ( **úlohy** okno podporuje také Objekt jazyka JavaScript promise).

- K ladění vláken v GPU, primárním nástrojem jsou **vláken GPU** systému windows.  
  
 V následující tabulce jsou uvedeny informace, které jsou k dispozici a akce, které můžete provádět v každé z těchto míst:  
  
|Uživatelské rozhraní|Informace o dostupné.|Akce, které můžete provádět|  
|--------------------|---------------------------|-----------------------------|  
|**Připojit k procesu** dialogové okno|K dispozici procesy, které můžete provést připojení k:<br /><br /> -Název procesu (.exe)<br />-Zpracování identifikační číslo<br />– Řádek nabídek název<br />-Type (spravované v4.0; Spravované v2.0, verze 1.1, verze 1.0; x86; x64; IA64)<br />-Uživatelské jméno (název účtu)<br />-Číslo relace|Vyberte proces pro připojení k<br /><br /> Vyberte vzdáleného počítače<br /><br /> Změnit typ přenosu pro připojení ke vzdáleným počítačům|  
|**Procesy** okna|Připojené procesy:<br /><br /> -Název procesu<br />-Zpracování identifikační číslo<br />-Path zpracovat .exe<br />– Řádek nabídek název<br />-Stavu (přerušení. Spuštění)<br />-Ladění (nativní, spravovat a tak dále.)<br />– Typ (výchozí, nativní bez jakéhokoli ověřování) přenosu<br />-Kvalifikátor transport (vzdálený počítač)|Nástroje:<br /><br /> -Připojení<br />-Odpojení<br />-Ukončení<br /><br /> Místní nabídky:<br /><br /> -Připojení<br />-Odpojení<br />-Odpojit při ladění zastavení<br />-Ukončení|  
|**Vlákna** okna|Vláken v aktuálním procesu:<br /><br /> -ID podprocesu<br />-Spravované ID<br />-Kategorie (hlavní vlákno, rozhraní přístup z více vláken, obslužnou rutinu volání vzdálených procedur nebo pracovní vlákno)<br />-Název přístup z více vláken<br />-Umístění, kde je vytvořen přístup z více vláken<br />-Priority<br />-Maska spřažení<br />-Pozastavenou počet<br />-Název procesu<br />-Příznak ukazatele<br />-Pozastavenou indikátoru|Nástroje:<br /><br /> -Vyhledávání<br />– Zásobník volání hledání<br />-Příznak pouze můj kód<br />-Výběr vlastní modul příznak<br />-Seskupit podle<br />-Columns<br />-Rozbalit nebo sbalit callstacks<br />-Rozbalit nebo sbalit skupiny<br />-Zablokování a roztání vláken<br /><br /> Místní nabídky:<br /><br /> -Zobrazení vláken ve zdroji<br />-Přepnout na vlákno<br />-Zmrazení spuštěných vláken<br />-Odblokování ukotvené vlákna<br />-Příznak vlákno pro další studie<br />-Odstranění označení vlákna<br />-Přejmenovat vlákna<br />-Zobrazení a skrytí vláken<br /><br /> Další akce:<br /><br /> -Zobrazení zásobníku volání vlákna v datového tipu|  
|Okno zdroje|Vlákno indikátory v levém mřížky znamenat jeden nebo více vláken (ve výchozím nastavení zapnutá pomocí místní nabídky v vypnuté **vláken** okna)|Místní nabídky:<br /><br /> -Přepnout na vlákno<br />-Příznak vlákno pro další studie<br />-Odstranění označení vlákna|  
|**Ladění umístění** panelu nástrojů|-Aktuální proces<br />-Pozastavit aplikace<br />-Obnovit aplikace<br />-Pozastavení a ukončení aplikace<br />-Aktuální vlákno<br />– Příznak stavu aktuální vlákno přepnutí<br />– Zobrazí jenom označení vlákna<br />-Zobrazit pouze aktuální proces<br />-Aktuální rámec zásobníku|-Přepnout na jiný proces<br />-Pozastavit, obnovit nebo vypnout aplikaci<br />-Přepnutí na jiné vlákno v aktuálním procesu<br />-Přepnout na jiný rámec zásobníku v aktuální vlákno<br />-Příznak nebo odstranění označení vlákna aktuální<br />– Zobrazí jenom označení vlákna<br />-Zobrazit pouze aktuální proces|  
|**Paralelní zásobníky** okna|-Zásobníky volání pro více vláken v jednom okně.<br />– Rámec zásobníku active pro každé vlákno.<br />-Volající a volané žádné metody.|-Vyfiltrovat zadaný vláken<br />-Přepnout do zobrazení úlohy<br />-Příznak nebo odstranění označení vlákna<br />-Přiblížení|   
|**Paralelní sledování** okna|-Příznak sloupec, ve kterém můžete označit vlákno, které chcete věnujte zvláštní pozornost.<br />-Sloupci rámec, ve kterém šipka Určuje vybraný snímek.<br />-Konfigurovat sloupec, který může zobrazit počítače, procesu, dlaždice, úloh a přístup z více vláken.|-Příznak nebo odstranění označení vlákna<br />– Zobrazí jenom označení vlákna<br />– Rámce přepínač<br />-Řazení sloupců<br />-Skupiny vláken<br />-Zablokování nebo odblokování vláken<br />-export dat v okna paralelního sledování| 
|**Úlohy** okna|-Zobrazení informací o <xref:System.Threading.Tasks.Task> objekty, včetně ID úlohy, stav úlohy (naplánováno, spuštění, čekání, zablokována), a které vlákno je přiřazen k úloze.<br />-Aktuální umístění v zásobníku volání.<br />-Delegáta předaný úlohu v okamžiku vytvoření|-Přepnout na aktuální úlohy<br />-Příznak nebo odstranění označení úlohu<br />-Zablokování nebo odblokování úlohu|  
|**Vlákna GPU** okna|-Příznak sloupec, ve kterém můžete označit vlákno, které chcete věnujte zvláštní pozornost.<br />-Aktuální vlákno sloupec, ve kterém žlutá šipka označuje aktuální vlákno.<br />-Na **počtu vláken** sloupec, který zobrazuje počet vláken ve stejném umístění.<br />-Na **řádku** sloupec, který zobrazí řádek kódu, kde se nachází každou skupinu vláken.<br />-Na **adresu** sloupec, který zobrazí adresa instrukce, kde se nachází každou skupinu vláken.<br />-Na **umístění** sloupec, který je umístění v kódu adresu.<br />-Na **stav** sloupec, který zobrazuje, zda vlákno je aktivní nebo blokované.<br />-Na **dlaždici** sloupec, který zobrazí dlaždice index pro vláken v řádku.|-Změnit na jiném podprocesu<br />– Zobrazí konkrétní dlaždice a přístup z více vláken<br />-Zobrazit nebo skrýt sloupce<br />-Řazení podle sloupce<br />-Skupiny vláken<br />-Zablokování nebo odblokování vláken<br />-Příznak nebo odstranění označení vlákna<br />– Zobrazí jenom označení vlákna|  
  
## <a name="see-also"></a>Viz také  
 [Připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Ladění kódu GPU](../debugger/debugging-gpu-code.md)