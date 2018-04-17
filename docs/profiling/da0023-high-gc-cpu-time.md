---
title: 'DA0023: Vysoký čas procesoru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0023
- vs.performance.23
- vs.performance.rules.DA0023
ms.assetid: aba875fe-9cbc-418d-a2c4-6eb47519a5bb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2fea32b5c1bf0f381c53f8b74c2d850b132e2f29
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="da0023-high-gc-cpu-time"></a>DA0023: Vysoký čas procesoru uvolňování paměti
|||  
|-|-|  
|Id pravidla|DA0023|  
|Kategorie|Použití rozhraní .NET framework|  
|Metoda profilace|Všechny|  
|Zpráva|Čas je vysoká. Tento údaj o nadměrné množství práce, kolekce paměti by mohly ovlivnit rychlost reakce aplikace. Můžete shromáždit .NET paměti přidělení objektů a dat životnost informace vzor přidělení paměti, které vaše aplikace používá lépe pochopit.|  
|Typ pravidla|Informační|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Data výkonu systému, která se shromažďují při vytváření profilu označuje, že množství času stráveného v uvolňování paměti je důležité ve srovnání s časem zpracování celkový počet aplikací.  
  
## <a name="rule-description"></a>Popis pravidla  
 Rozhraní Microsoft .NET běžné language runtime (CLR) poskytuje mechanismus správy automatické paměti, který používá systém uvolňování paměti pro uvolnění paměti objekty, které aplikace se už používá. Uvolňování paměti je orientované na generování založen na předpokladu, že jsou krátkodobou mnoho přidělení. Lokální proměnné, například by měl mít krátkodobé trvání. Spustit nově vytvořené objekty v generaci 0 (0. generace) a pak průběhu generace 1, pokud se uvolňování paměti spusťte a nakonec přechodu na 2. generace zvládnout situaci, kdy aplikace je stále používá.  
  
 Objekty v generace 0 se shromažďují často a obvykle velmi efektivně. Objekty v generace 1 se shromažďují méně často a méně efektivní. Nakonec dlohotrvající objekty v generace 2 by měl být shromažďovány i méně často. 2. generace kolekce, což je úplná uvolňování spustit, je také nejvíce náročná operace.  
  
 Toto pravidlo aktivuje se v případě množství času stráveného v uvolňování paměti je důležité ve srovnání s časem zpracování celkový počet aplikací.  
  
> [!NOTE]
>  Když se nadměrnému podíl času stráveného v uvolňování paměti porovná se bude čas zpracování celkový počet aplikací [DA0024: nadměrný čas procesoru](../profiling/da0024-excessive-gc-cpu-time.md) aktivuje upozornění místo toto pravidlo.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [značky zobrazení](../profiling/marks-view.md) profilování data. Najít **využívání paměti rozhraním .NET CLR\\% čas** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu kde režií při uvolňování paměti spravované paměti je větší než ostatní fáze. Porovnejte hodnoty % čas hodnoty na míru uvolňování uvedený v **# 0. generace kolekce**, **Počet úklidů 1. generace**, **Počet úklidů 2. generace** hodnoty .  
  
 % Času v hodnotě GC se pokusí množství času, který aplikace tráví provádění uvolňování úměrná celkový objem zpracování sestavy. Uvědomte si, že existují okolnosti, kdy % času v hodnotě GC může hlásit na velmi vysokou hodnotu, ale není z důvodu nadměrného uvolňování paměti. Další informace o způsobu, jímž % času v hodnotě uvolňování paměti se počítá najdete v tématu [rozdíl mezi výkonu dat hlášené různých nástrojů - 4](http://go.microsoft.com/fwlink/?LinkId=177863) položku **Maoni na Weblogu** na webu MSDN. Pokud se vyskytnou chyby stránky nebo aplikace se během uvolňování paměti přepnuto jinou vyšší prioritu práci na počítači, bude odrážet % času v čítači GC tyto další zpoždění.