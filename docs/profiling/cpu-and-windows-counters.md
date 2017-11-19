---
title: "Windows čítače procesoru a | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.counters
helpviewer_keywords:
- Windows counters in Profiling Tools
- CPU counters in Profiling Tools
ms.assetid: d2c45c6a-f975-45ab-b8a5-4768ddd518fb
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62889012c5640fb0f29eadb6f70e678f941ff286
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="cpu-and-windows-counters"></a>Čítače procesoru a systému Windows
Visual Studio Profiler umožňuje shromažďovat údaje o výkonu, který byl vytvořen v operačním systému (čítače systému Windows) a data výkonu vygenerovaná jednotky procesoru (čítače CPU).  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="windows-counters"></a>Čítače systému Windows  
 Čítače systému Windows jsou součástí Windows diagnostiky infrastrukturu, která poskytuje informace o výkonu operačního systému nebo aplikace, služby nebo ovladače. Čítače systému Windows bude záviset na konfiguraci aktuálního počítače a nemusí být k dispozici na jiných počítačích. Čítače výkonu systému Windows se shromažďují v profilaci datové soubory jako profilace značky, které se dají použít k filtrování zobrazení a sestavy.  
  
## <a name="cpu-counters"></a>Čítače CPU  
 Čítače procesoru jsou funkce procesoru počítače, které uloží počet událostí související s hardwarem.  Při shromažďování dat čítačů procesoru pomocí metoda profilování instrumentace, připojí se k data pro funkce a moduly data. Můžete shromáždit více čítačů procesoru pomocí metody instrumentace. Při použití metody vzorkování, je třeba vybrat jeden čítač se má použít jako události se odeberou.  
  
 Čítače výkonu jsou specifické pro procesor. Výrazně odlišné konfigurace nastavení pro povolení ke stejnému čítači výkonu mohou obsahovat různé modely a verzích Procesorem. [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]Přenosné události profileru oddělte pár běžných čítačů výkonu z konkrétní procesory a umožňují shromažďovat nebo ukázkové události obecné výkonu.  
  
 Pokud chcete spočítat určitá událost při použití profileru, například Neúspěšné přístupy do mezipaměti L2, můžete vytvořit relaci výkonu kolem tohoto odesílatele událostí. Můžete provést na libovolném procesoru s L2 mezipaměti. Výkonnostní relace lze přesunout z platformách bez úprav.  
  
 Visual Studio profiler i nadále podporuje konkrétní události pro konkrétní platformu. Třeba vývojář na platformě Pentium 4 chtít počet událostí, které jsou specifické pro architekturu NetBurst. Tato událost není přenosné, ale stále k dispozici pro vývojáře pro konkrétní výkonnostní relace na konkrétní platformu.  
  
## <a name="portable-and-platform-events"></a>Přenositelností a události platformy  
 Přenosné události jsou skupiny čítačů procesoru, které nejsou specifické pro specifické procesory. Všechny ostatní čítače CPU se nazývají události platformy a nemusí být podporován na různých platformách.  
  
 Čítače pro platformu a přenositelností události jsou definovány v. Soubory XML, které jsou k dispozici konkrétní hodnoty, které se vztahují k počítadla. Existuje více souborů pro různé procesory, protože data pro Intel a AMD procesorů, například se liší. [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)] Profileru používá tuto informaci k příslušné čítače přenositelností a platformy, k dispozici pro uživatele pro měření výkonu.  
  
### <a name="portable-events"></a>Přenosné události  
 Přenosné události obsahují následující události:  
  
 **Obecné události**  
  
|Název události|Popis události|  
|----------------|-----------------------|  
|Vyřazení pokyny|Označuje počet pokyny, které provést, dokud se nedokončí události.|  
|Bez zastavený cyklů|Označuje pouze cykly, ve kterých procesoru nebyla zastavena, například čekání na vstupně-výstupní operace.|  
  
 **Front-endu události**  
  
|Název události|Popis události|  
|----------------|-----------------------|  
|ITLB neúspěchy|Označuje číslo, hledání instrukce překlad vzhled vyhraďte vyrovnávací paměti, které vedly k neúspěšnému přístupu.|  
  
 **Větev událostí**  
  
|Název události|Popis události|  
|----------------|-----------------------|  
|Vyřazeno větví|Označuje počet pokyny firemní pobočky provést, dokud se nedokončí události.|  
|Nemá předpokládaných větví|Označuje nemá předpokládaných větve, které dojít, protože procesor předpovědět nesprávnou cestu. Nemá předpokládaných větví ovlivnit výkon, protože procesor musí zahodit všechny práci a znovu spustit na správnou cestu.|  
  
 **Události paměti:**  
  
|Název události|Popis události|  
|----------------|-----------------------|  
|L2 Neúspěšné přístupy mezipaměti pro čtení|Označuje, že počet druhé úrovně mezipaměti čtení neúspěšných přístupů.|  
|L2 Mezipaměti pro čtení odkazy|Označuje, že počet druhé úrovně mezipaměti čtení odkazy. Zahrnuje neúspěchy zatížení a číst pro neúspěchy vlastnictví (předpisy RRO) a přístupů.|  
  
## <a name="viewing-available-counters"></a>Zobrazení k dispozici čítače  
 V okně příkazového řádku, můžete vytvořit seznam na k dispozici čítače CPU v prostředí Visual Studio IDE.  
  
### <a name="visual-studio-ui"></a>Visual Studio uživatelského rozhraní  
 Seznam dostupných čítačů na počítač v prostředí Visual Studio IDE, musí mít relaci profileru výkonu, otevřete v Průzkumníku výkonu.  
  
##### <a name="to-view-a-list-of-a-list-of-all-cpu-counters-that-are-supported-on-the-current-platform"></a>Chcete-li zobrazit seznam seznam všech čítačů procesoru, které jsou podporovány na aktuální platformě  
  
1.  Prohlížeč výkonu, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na **vlastnosti**.  
  
2.  Proveďte jednu z těchto akcí:  
  
    -   Klikněte na tlačítko **vzorkování**a potom vyberte **čítače výkonu** z **ukázka** seznam událostí. Čítače CPU jsou uvedeny v **čítače výkonu k dispozici**.  
  
         **Poznámka:** klikněte na tlačítko **zrušit** vrátit na předchozí konfiguraci vzorkování.  
  
     -nebo-  
  
    -   Vyberte **čítače CPU**a potom vyberte **shromažďování čítače CPU**. Čítače CPU jsou uvedeny v **dostupné čítače**.  
  
         **Poznámka:** klikněte na tlačítko **zrušit** vrátit k předchozí konfiguraci kolekce čítače.  
  
##### <a name="to-view-a-list-of-a-list-of-window-counters-that-are-supported-on-the-current-platform"></a>Chcete-li zobrazit seznam seznam čítačů okno, které jsou podporovány na aktuální platformě  
  
1.  Prohlížeč výkonu, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na **vlastnosti**.  
  
2.  Klikněte na tlačítko **čítačů systému Windows**.  
  
3.  Vyberte **shromažďování čítačů systému Windows**.  
  
4.  Z **kategorie čítače** seznamu, vyberte skupinu čítače. Čítače systému Windows pro skupinu se zobrazí v seznamu.  
  
     **Poznámka:** klikněte na tlačítko **zrušit** vrátit k předchozí konfiguraci kolekce čítače.  
  
### <a name="command-line"></a>Příkazový řádek  
 Pomocí [VSPerfCmd](../profiling/vsperfcmd.md) nástroj příkazového řádku, můžete vytvořit seznam čítačů procesoru, které jsou k dispozici v počítači z příkazového řádku.  
  
##### <a name="to-list-of-cpu-counters-that-are-supported-on-the-current-platform"></a>Seznam čítačů procesoru, které jsou podporovány na aktuální platformě musí  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Typ  
  
     **\<Visual Studio výkonu nástroje Directory > \VSPerfCmd /querycounters**  
  
     kde  **\<Visual Studio výkonu nástroje Directory >** obvykle představuje cestu k adresáři nástroje pro sledování výkonu instalace sady Visual Studio  
  
     C:\Program Files\Microsoft Visual Studio 10.0\Team nástroje nástroje  
  
## <a name="see-also"></a>Viz také  
 [Přehled](../profiling/overviews-performance-tools.md)   
 [Postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md)   
 [Postupy: shromažďování dat čítačů procesoru](../profiling/how-to-collect-cpu-counter-data.md)   
 [Postupy: shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)