---
title: 'DA0021: Vysoká míra 1. generace kolekce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.21
- vs.performance.DA0021
- vs.performance.rules.DA0021
ms.assetid: ebf5d9b3-a1ac-4688-8f0f-39a85f4dd15f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4fe9c0557b7bc7ce366f2652e83b671ba813db69
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750061"
---
# <a name="da0021-high-rate-of-gen-1-garbage-collections"></a>DA0021: Vysoká míra 1. generace kolekce pamětí
|||  
|-|-|  
|Id pravidla|DA0021|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Všechny|  
|Zpráva|Je velmi vysoká míra 1. generace uvolňování pamětí, ke kterým dochází. Pokud návrh většinu datových struktur s vaším programem přidělovány a trvalé po dlouhou dobu, to není normálně problém. Ale pokud toto chování nezamýšleným, vaše aplikace může být Připnutí objekty. Pokud si nejste jisti, můžete shromáždit .NET paměti přidělení objektů a dat životnost informace pochopit vzor přidělení paměti, které vaše aplikace používá.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Data výkonu systému, která nebyla shromážděna během profilace znamenat, že byl uvolnit značná část paměti for.NET Framework objekty v 1. generace uvolňování ve srovnání s shromažďování dat 0. generace.  
  
## <a name="rule-description"></a>Popis pravidla  
 Rozhraní Microsoft .NET běžné language runtime (CLR) poskytuje mechanismus správy automatické paměti, který používá systém uvolňování paměti pro uvolnění paměti objekty, které aplikace se už používá. Uvolňování paměti je orientované na generování založen na předpokladu, že jsou krátkodobou mnoho přidělení. Lokální proměnné, například by měl mít krátkodobé trvání. Spustit nově vytvořené objekty v generaci 0 (0. generace) a pak průběhu generace 1, pokud se uvolňování paměti spusťte a nakonec přechodu na 2. generace zvládnout situaci, kdy aplikace je stále používá.  
  
 Objekty v generace 0 se shromažďují často a obvykle velmi efektivně. Objekty v generace 1 se shromažďují méně často a méně efektivní. Nakonec dlohotrvající objekty v generace 2 by měl být shromažďovány i méně často. 2. generace kolekce, což je úplná uvolňování spustit, je také nejvíce náročná operace.  
  
 Toto pravidlo aktivuje se při úměrně příliš mnoho generace 1 kolekce došlo. Pokud příliš mnoho objektů poměrně krátkodobou zůstanou platné i po 0. generace kolekce, ale se pak můžou být shromážděny v kolekci generace 1, se může stát nadměrné náklady na správu paměti. Další informace najdete v tématu [střední životnosti krizové](http://go.microsoft.com/fwlink/?LinkId=177835) můžete zveřejnit na Mariani Portoriku výkonu Tidbits na webu MSDN.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [značky zobrazení](../profiling/marks-view.md) profilování data. Najít **využívání paměti rozhraním .NET CLR\\# 0. generace kolekce** a **využívání paměti rozhraním .NET CLR\\Počet úklidů 1. generace** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu místo, kde uvolňování dochází častěji. Tyto hodnoty k porovnání **% čas** sloupec Pokud vzor spravované paměti přidělené nezpůsobuje režie na správu příliš mnoho paměti.  
  
 Zjistit aplikace vzor využití spravované paměti profilu ho znovu spuštěn přidělení paměti a.NET profil a žádosti o měření doba života objektu.  
  
 Informace o tom, jak zlepšit výkon kolekce paměti najdete v tématu [základní informace o systém uvolňování paměti a výkon pomocné parametry](http://go.microsoft.com/fwlink/?LinkId=148226) na webu společnosti Microsoft. Informace o nároky na automatické uvolňování paměti najdete v tématu [velkého objektu haldy neodkrytých](http://go.microsoft.com/fwlink/?LinkId=177836).