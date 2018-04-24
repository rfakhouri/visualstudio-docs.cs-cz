---
title: 'Postupy: výběr metod kolekcí | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, choosing collection method
- profiling tools, choosing collection method
- performance collection methods
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 55e801404fbf3356b597471d7c3dda23264eb0c5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-choose-collection-methods"></a>Postupy: Výběr metod kolekcí

Visual Studio Tools profilace podporují tři metody shromažďování dat o výkonu: vzorkování, instrumentace a souběžnosti. Metoda vzorkování nebo instrumentace můžete použít také ke shromažďování dat paměti přidělení a dobu života rozhraní .NET.

Můžete použít výkonnostní relace **metoda** vlastnosti a určit nejvhodnější metody collection pro vaši aplikaci. Můžete nastavit metodu kolekce z Průvodce výkonu, prohlížeč výkonu, nebo ze stránek vlastností výkonnostní relace. Pokud používáte nástroje příkazového řádku, přečtěte si téma [profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md) Další informace.

## <a name="performance-wizard"></a>Průvodce výkonu

### <a name="to-select-a-collection-method-using-the-performance-wizard"></a>Vyberte metodu kolekce pomocí průvodcem výkonu

- Na první stránce průvodce vyberte jednu z následujících možností:

|Možnost|Popis|
|------------|-----------------|
|**Vzorkování procesoru**|Shromažďuje statistiky aplikace, které jsou užitečné pro počáteční analýzy a analyzovat problémy využití procesoru.|
|**Instrumentace**|Shromažďuje podrobné časování data, která jsou užitečné pro přesně zacílené analýzy a analýza problémů s výkonem vstupu a výstupu.|
|**Přidělení paměti .NET**|Shromažďuje [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] dat přidělení paměti pomocí metoda profilování se vzorkováním.|
|**Souběžnost**|Shromažďuje data kolizí číselné prostředků.|

## <a name="performance-explorer"></a>Prohlížeč výkonu

### <a name="to-select-a-collection-method-using-performance-explorer"></a>Vyberte metodu kolekce pomocí prohlížeč výkonu

1. Na **prohlížeč výkonu** nástrojů, klikněte na šipku vedle položky **metoda** rozevíracího seznamu.

2. Klikněte na preferovanou metodu kolekce.

## <a name="performance-session-property-pages"></a>Stránky vlastností relace výkonu

### <a name="to-select-the-sampling-or-instrumentation-method-using-performance-session-properties"></a>Chcete-li vybrat metodu vzorkování nebo instrumentace pomocí vlastnosti výkonnostní relace

1. V **prohlížeč výkonu**, vyberte výkonnostní relace.

     Název souboru relace výkonu má příponu .psess.

2. Klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na **vlastnosti**.

3. V **stránky vlastností**, klikněte na tlačítko **Obecné**.

4. Klikněte na preferovanou metodu kolekce.

    - Informace o dalších možnostech, které jsou k dispozici, při shromažďování dat vzorkování najdete v tématu [shromažďování statistik výkonu pomocí pomocí vzorkování](../profiling/collecting-performance-statistics-by-using-sampling.md)

    - Informace o dalších možnostech, které jsou k dispozici, při shromažďování dat vzorkování najdete v tématu [shromažďování podrobných dat časování pomocí instrumentace pomocí](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md).

### <a name="to-select-net-memory-data-collection-by-using-performance-session-properties"></a>Chcete-li vybrat shromažďování dat paměti .NET pomocí vlastnosti výkonnostní relace

1. V **prohlížeč výkonu**, vyberte výkonnostní relace.

     Název souboru relace výkonu má příponu .psess.

2. Klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na **vlastnosti**.

3. V **stránky vlastností**, klikněte na tlačítko **Obecné**.

4. Klikněte na tlačítko **vzorkování** nebo **instrumentace**.

5. Klikněte na tlačítko **.NET shromažďování informací o přidělení objektu** shromažďovat velikost a počet [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] objektu přidělení.

6. (Volitelné) Klikněte na tlačítko **taky shromažďovat informace o doba života objektu .NET** ke shromažďování dat o generace uvolňování paměti kolekce, ve kterých byl objekt paměť uvolnit.

     Informace o dalších možnostech, které jsou k dispozici, při shromažďování dat paměti .NET najdete v tématu [shromažďování přidělení paměti .NET a životnosti](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md).

### <a name="to-select-concurrency-data-collection-by-using-performance-session-properties"></a>Chcete-li vybrat shromažďování dat souběžnosti pomocí vlastnosti výkonnostní relace

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **Obecné**.

3. Klikněte na tlačítko **souběžnosti**.

## <a name="see-also"></a>Viz také

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[Porozumění hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)  
[Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)