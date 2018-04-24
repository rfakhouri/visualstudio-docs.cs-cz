---
title: 'DA0018: 32bitová aplikace spuštěná v procesu limitech paměti spravovaného | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.18
- vs.performance.DA0018
- vs.performance.rules.DA0018
ms.assetid: 98eb2d96-f92f-42f9-915c-e5ac2330ffbf
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: ba328ae4b54728422e032741e20543b99f49d5ae
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="da0018-32-bit-application-running-at-process-managed-memory-limits"></a>DA0018: 32bitová aplikace spuštěná v limitech paměti spravovaného procesu
|||  
|-|-|  
|Id pravidla|DA0018|  
|Kategorie|Použití nástroje pro profilaci|  
|Metoda profilace|Vzorkování|  
|Zpráva|Spravované přidělení paměti blíží výchozí limit pro 32bitový proces. Aplikace může být vázané na paměť.|  
|Typ pravidla|Upozornění|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Systému data shromážděná během spuštění profilování označuje, že paměti rozhraní .NET Framework haldách dosaženy maximální velikost, spravované haldách dosáhnout v 32bitový proces. Tento maximální velikost je výchozí hodnota. Je založena na celkovém množství adresního prostoru procesu, který může být přidělen pro nesdílených bajtů. Hodnota hlášené maximální pozorovanou hodnotu haldách během procesu PROFILOVANÉHO byl aktivní. Vezměte v úvahu profilace znovu pomocí metody profilace paměti .NET a optimalizace použití spravované prostředky v aplikaci.  
  
 Při velikosti spravovaný haldách přístupu výchozí limit, proces shromažďování automatické paměti pravděpodobně má být vyvolána častěji. Tím se zvyšuje režii správy paměti.  
  
 Toto pravidlo aktivuje pouze pro 32bitové aplikace spuštěné na 32bitové počítače.  
  
## <a name="rule-description"></a>Popis pravidla  
 Rozhraní Microsoft .NET běžné language runtime (CLR) poskytuje mechanismus správy automatické paměti, který používá systém uvolňování paměti pro uvolnění paměti objekty, které aplikace se už používá. Uvolňování paměti je orientované na generování založen na předpokladu, že jsou krátkodobou mnoho přidělení. Lokální proměnné, například by měl mít krátkodobé trvání. Spustit nově vytvořené objekty v generaci 0 (0. generace) a pak průběhu generace 1, pokud se uvolňování paměti spusťte a nakonec přechodu na 2. generace zvládnout situaci, kdy aplikace je stále používá.  
  
 Spravované objekty, které jsou větší než 85 KB jsou přiděleny na velkého objektu haldy, tam, kde jsou předmětem méně častá uvolňování paměti a komprimace než menší objekty. rozsáhlé objekty jsou spravovány samostatně, se předpokládá, že jsou více trvalé a protože kombinace trvalé a velké objekty se často přidělené menší objekty může vytvořit nejhorší přetypování fragmentace haldy.  
  
 Celková velikost spravovaný haldách přístupu výchozí limit, režijní náklady správy paměti obvykle zvyšuje do bodu, kde je možné spustit mít vliv na rychlost reakce a škálovatelnost aplikace.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Klikněte dvakrát na zprávy v okně Seznam chyb navigaci na [značky](../profiling/marks-view.md) zobrazení. Najít **využívání paměti rozhraním .NET CLR\\# bajtů ve všech haldách** a **# celkový počet zapsaných bajtů** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu kde přidělení spravované paměti je větší než ostatní fáze. Porovnejte hodnoty **# bajtů ve všech haldách** sloupec, který se počet uvolňování uvedený v **využívání paměti rozhraním .NET CLR\\# 0. generace kolekce**, **.NET CLR paměti\\Počet úklidů 1. generace**, a **využívání paměti rozhraním .NET CLR\\Počet úklidů 2. generace** sloupce, abyste zjistili, pokud vzor spravované paměti přidělené ovlivňuje rychlost uvolňování paměti kolekce.  
  
 V aplikaci rozhraní .NET Framework, modul common language runtime omezuje celková velikost spravovaných haldách na mírně méně než polovinu maximální velikost části privátní oblast adresního prostoru procesu. 2 GB pro 32bitovými procesy spuštěné na počítači 32-bit, představuje horní limit počtu soukromá část adresní prostor procesu. Celková velikost spravovaných haldách začne přístupu jeho výchozí limit, může zvýšit režií při správě paměti a může snížit výkon aplikace.  
  
 Pokud režijní náklady na příliš mnoho spravované paměti k potížím, zvažte jednu z těchto možností:  
  
-   Optimalizace využití aplikace spravované paměťových prostředků  
  
     -nebo-  
  
-   pořízení postup snížit architektury omezení na maximální velikost virtuální paměti pro 32bitový proces  
  
 Optimalizace využití aplikace spravované paměťových prostředků, shromažďování dat přidělení spravované paměti v rozhraní .NET přidělení paměti profilaci spustit. Zkontrolujte [zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md) sestavy pochopit aplikace vzor přidělení paměti.  
  
 Použití [zobrazení doby života objektu](../profiling/object-lifetime-view.md) zjistíte, které program dat objekty jsou zachované do generace a potom uvolnit z ní.  
  
 Použití [přidělení – zobrazení](../profiling/dotnet-memory-allocations-view.md) k určení cesty provádění, jejichž výsledkem rozdělení těchto prostředků.  
  
 Další informace o tom, jak zlepšit výkon kolekce paměti najdete v článku technické rozhraní .NET Framework, [základní informace o systém uvolňování paměti a výkon pomocné parametry](http://go.microsoft.com/fwlink/?LinkId=177946) na webu MSDN.  
  
 K získání architektury pomoc z omezení virtuální paměti na velikosti části privátního adresního prostoru procesu, opakujte spuštění tohoto procesu 32-bit na 64bitový počítač.  32bitový proces na 64bitový počítač můžete získat až 4 GB privátní virtuální paměti.  
  
 64bitový proces běží na 64bitový počítač můžete získat až 8 TB virtuální paměti. Vezměte v úvahu znovu kompilace aplikace pro spuštění jako nativní 64bitové aplikace. Toto pravidlo je pouze informativní a nemusejí být nutné opravné akce.