---
title: "DA0022: Vysoká míra 2. generace kolekce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0022
- vs.performance.rules.DA0022
- vs.performance.22
ms.assetid: f871a547-0e6f-4b11-b2d7-174d30fc2ed8
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2917ed46a32a6f726a5b484bb1d91e7e277854c1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="da0022-high-rate-of-gen-2-garbage-collections"></a>DA0022: Vysoká míra 2. generace kolekce pamětí
|||  
|-|-|  
|Id pravidla|DA0022|  
|Kategorie|Použití rozhraní .NET framework|  
|Metoda profilace|Všechny|  
|Zpráva|Je velmi vysoká míra 2. generace uvolňování pamětí, ke kterým dochází. Pokud návrh většinu datových struktur s vaším programem přidělovány a trvalé po dlouhou dobu, to není normálně problém. Ale pokud toto chování nezamýšleným, vaše aplikace může být Připnutí objekty. Pokud si nejste jisti, můžete shromáždit .NET paměti přidělení objektů a dat životnost informace pochopit vzor přidělení paměti, které vaše aplikace používá.|  
|Typ pravidla|Upozornění|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Data výkonu systému, která nebyla shromážděna během profilace znamenat, že byla v 2. generace uvolňování paměti ve srovnání s generace 0 a 1. generace kolekce uvolnit značná část paměti for.NET Framework objekty.  
  
## <a name="rule-description"></a>Popis pravidla  
 Rozhraní Microsoft .NET běžné language runtime (CLR) poskytuje mechanismus správy automatické paměti, který používá systém uvolňování paměti pro uvolnění paměti objekty, které aplikace se už používá. Uvolňování paměti je orientované na generování založen na předpokladu, že jsou krátkodobou mnoho přidělení. Lokální proměnné, například by měl mít krátkodobé trvání. Spustit nově vytvořené objekty v generaci 0 (0. generace) a pak průběhu generace 1, pokud se uvolňování paměti spusťte a nakonec přechodu na 2. generace zvládnout situaci, kdy aplikace je stále používá.  
  
 Objekty v generace 0 se shromažďují často a obvykle velmi efektivně. Objekty v generace 1 se shromažďují méně často a méně efektivní. Nakonec dlohotrvající objekty v generace 2 by měl být shromažďovány i méně často. 2. generace kolekce, což je úplná uvolňování spustit, je také nejvíce náročná operace.  
  
 Toto pravidlo aktivuje se při úměrně příliš mnoho generace 2 kolekce dochází. Které jsou v pořádku .NET Framework – aplikace bude mít více než 5 třikrát tolik generace 1 kolekce jako 2. generace kolekce. (10 x faktor je pravděpodobně ideální.)  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [značky zobrazení](../profiling/marks-view.md) profilování data. Najít **využívání paměti rozhraním .NET CLR\\# 0. generace kolekce** a **využívání paměti rozhraním .NET CLR\\Počet úklidů 1. generace** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu místo, kde uvolňování dochází častěji. Tyto hodnoty k porovnání **% čas** sloupec Pokud vzor spravované paměti přidělené nezpůsobuje režie na správu příliš mnoho paměti.  
  
 Vysoký podíl generace 2 kolekce není vždy problém. Může to být záměrné. Aplikace, která přiděluje struktury velkého množství dat, které musí zůstat aktivní dlouhou dobu během provádění může spustit toto pravidlo. Pokud takové aplikace je přetížena paměť, může vynutit provést časté kolekce. Pokud levnější generace 0 a 1. generace kolekce můžete získat pouze malé množství spravované paměť, bude naplánována častější kolekce generace 2.  
  
 Existují další využívání paměti rozhraním .NET CLR sloupce v zobrazení značky, které pomáhají identifikovat problémy kolekce paměti. **% Čas** sloupec vám pomůže pochopit dochází k tom, kolik paměti režie na správu. Pokud vaše aplikace používá obvykle poměrně malý počet velkých ale trvalé objekty, neměl spotřebovávat časté kolekce generace 2 nadměrnému využití procesoru. Pokud aplikace je přetížena paměť, protože další fyzické paměti (RAM) je požadované související pravidel, která se vyhodnotí **Paměť\Stránky/s** hodnoty ve sloupcích může také provést.  
  
 Zjistit aplikace vzor využití spravované paměti profilu ho znovu spuštěn profil přidělení paměti a.NET a vyberte doba života objektu profilace možnost.  
  
 Informace o tom, jak zlepšit výkon kolekce paměti najdete v tématu [základní informace o systém uvolňování paměti a výkon pomocné parametry](http://go.microsoft.com/fwlink/?LinkId=148226) na webu společnosti Microsoft. Informace o nároky na automatické uvolňování paměti najdete v tématu [velkého objektu haldy neodkrytých](http://go.microsoft.com/fwlink/?LinkId=177836).