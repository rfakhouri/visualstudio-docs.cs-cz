---
title: 'DA0005: Časté kolekce GC2 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0005
- vs.performance.rules.DAManyGC2Collections
- vs.performance.5
- vs.performance.rules.DA0005
ms.assetid: 8d3f267c-8a74-4cf4-91a5-0b06a76dc2bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 023f61c3c20e47b48f975e247ad2c649bbbf7f38
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="da0005-frequent-gc2-collections"></a>DA0005: Časté kolekce GC2
|||  
|-|-|  
|RuleId|DA0005|  
|Kategorie|Použití rozhraní .NET framework|  
|Metoda profilace|Využívání paměti rozhraním .NET|  
|Zpráva|Mnoho objektů jsou shromažďovány v uvolňování paměti generace 2.|  
|Typ zprávy|Upozornění|  
  
## <a name="cause"></a>příčina  
 Vysoký počet objekty paměti .NET jsou se uvolní v uvolňování paměti generace 2.  
  
## <a name="rule-description"></a>Popis pravidla  
 Rozhraní Microsoft .NET common language runtime (CLR) poskytuje mechanismus správy automatické paměti, který používá systém uvolňování paměti pro uvolnění paměti objekty, které aplikace se už používá. Uvolňování paměti je orientované na generování založen na předpokladu, že jsou krátkodobou mnoho přidělení. Lokální proměnné, například by měl mít krátkodobé trvání. Spustit nově vytvořené objekty v generaci 0 (0. generace) a pak průběhu generace 1, pokud se uvolňování paměti spusťte a nakonec přechodu na 2. generace zvládnout situaci, kdy aplikace je stále používá.  
  
 Objekty v generace 0 se shromažďují často a obvykle velmi efektivně. Objekty v generace 1 se shromažďují méně často a méně efektivní. Nakonec dlohotrvající objekty v generace 2 by měl být shromažďovány i méně často. 2. generace kolekce, což je úplná uvolňování spustit, je také nejvíce náročná operace.  
  
 Toto pravidlo aktivuje se při úměrně příliš mnoho generace 2 kolekce došlo. Pokud příliš mnoho objektů relativně krátkodobou zůstanou platné i po 1. generace kolekce, ale se pak můžou být shromážděny v kolekci úplné 2. generace, náklady na správu paměti můžete snadno stát nadměrné. Další informace najdete v tématu [střední životnosti krizové](http://go.microsoft.com/fwlink/?LinkId=177835) můžete zveřejnit na Mariani Portoriku výkonu Tidbits na webu MSDN.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Zkontrolujte [zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md) sestavy pochopit aplikace vzor přidělení paměti. Použití [zobrazení doby života objektu](../profiling/object-lifetime-view.md) zjistíte, které program dat objekty jsou zachované do 2. generace a potom uvolnit z ní. Použití [přidělení – zobrazení](../profiling/dotnet-memory-allocations-view.md) k určení cesty provádění, jejichž výsledkem rozdělení těchto prostředků.  
  
 Informace o tom, jak zlepšit výkon kolekce paměti najdete v tématu [základní informace o systém uvolňování paměti a výkon pomocné parametry](http://go.microsoft.com/fwlink/?LinkId=148226) na webu společnosti Microsoft. Informace o nároky na automatické uvolňování paměti najdete v tématu [velkého objektu haldy neodkrytých](http://go.microsoft.com/fwlink/?LinkId=177836).