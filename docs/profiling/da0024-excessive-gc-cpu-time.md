---
title: 'DA0024: Nadměrný čas procesoru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0024
- vs.performance.24
- vs.performance.rules.DA0024
ms.assetid: 228872da-77d0-4da5-b455-ac57fb1867c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9abd80ff9d29c558f50eef0f80ad46e868180596
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766113"
---
# <a name="da0024-excessive-gc-cpu-time"></a>DA0024: Čas nadměrný procesoru uvolňování paměti
|||  
|-|-|  
|Id pravidla|DA0024|  
|Kategorie|Použití rozhraní .NET framework|  
|Metoda profilace|Všechny|  
|Zpráva|Čas je velmi vysoká. Je nadměrné množství paměti kolekce režii.|  
|Typ pravidla|Upozornění|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Data výkonu systému, která nebyla shromážděna během profilace označuje, že množství času strávené v uvolňování paměti je příliš vysoké ve srovnání s časem zpracování celkový počet aplikací.  
  
## <a name="rule-description"></a>Popis pravidla  
 Rozhraní Microsoft .NET běžné language runtime (CLR) poskytuje mechanismus správy automatické paměti, který používá systém uvolňování paměti pro uvolnění paměti objekty, které aplikace se už používá. Uvolňování paměti je orientované na generování založen na předpokladu, že jsou krátkodobou mnoho přidělení. Lokální proměnné, například by měl mít krátkodobé trvání. Spustit nově vytvořené objekty v generaci 0 (0. generace) a pak průběhu generace 1, pokud se uvolňování paměti spusťte a nakonec přechodu na 2. generace zvládnout situaci, kdy aplikace je stále používá.  
  
 Objekty v generace 0 se shromažďují často a obvykle velmi efektivně. Objekty v generace 1 se shromažďují méně často a méně efektivní. Nakonec dlohotrvající objekty v generace 2 by měl být shromažďovány i méně často. 2. generace kolekce, což je úplná uvolňování spustit, je také nejvíce náročná operace.  
  
 Toto pravidlo aktivuje se v případě množství času strávené v uvolňování paměti je příliš vysoká ve srovnání s časem zpracování celkový počet aplikací.  
  
> [!NOTE]
>  Když podíl času stráveného v uvolňování paměti je důležité, ale není příliš ve srovnání s bude čas zpracování celkový počet aplikací [DA0023: vysoký čas procesoru](../profiling/da0023-high-gc-cpu-time.md) aktivuje upozornění místo toto pravidlo.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [značky zobrazení](../profiling/marks-view.md) profilování data. Najít **využívání paměti rozhraním .NET CLR\\% čas** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu kde režií při uvolňování paměti spravované paměti je větší než ostatní fáze. Porovnejte hodnoty % čas hodnoty na míru uvolňování uvedený v **# 0. generace kolekce**, **Počet úklidů 1. generace**, **Počet úklidů 2. generace** hodnoty .  
  
 % Času v hodnotě GC se pokusí množství času, který aplikace tráví provádění uvolňování úměrná celkový objem zpracování sestavy. Uvědomte si, že existují okolnosti, kdy % času v hodnotě GC může hlásit vysoké hodnoty, ale není z důvodu nadměrného uvolňování paměti. Další informace o způsobu, jímž % času v hodnotě uvolňování paměti se počítá najdete v tématu [rozdíl mezi výkonu dat hlášené různých nástrojů - 4](http://go.microsoft.com/fwlink/?LinkId=177863) položku **Maoni na Weblogu** na webu MSDN. Pokud se vyskytnou chyby stránky nebo aplikace je zrušeny podle jinou vyšší prioritu práci na počítači během uvolňování paměti, se projeví % času v čítači GC tyto další zpoždění.