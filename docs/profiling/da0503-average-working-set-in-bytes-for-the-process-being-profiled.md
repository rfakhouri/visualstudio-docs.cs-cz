---
title: "DA0503: Průměr pracovní sady v bajtech pro profilovaný proces | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.503
- vs.performance.DA0503
- vs.performance.rules.DA0503
ms.assetid: 9047a494-eaaf-4679-b422-c64e8bde77a4
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3c5333a6ce2ddfa5e3d627030e71466a8c9ae0c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0503-average-working-set-in-bytes-for-the-process-being-profiled"></a>DA0503: Průměr Pracovní sady v bajtech pro profilovaný Proces
|||  
|-|-|  
|Id pravidla|DA0503|  
|Kategorie|Sledování prostředků|  
|Metoda profilace|Všechny|  
|Zpráva|Tyto informace byly získány pouze pro informaci. Čítač pracovní sady procesu měří využití fyzické paměti procesem, které jsou profilace. Hodnota hlášené je počítaný průměrem přes všechny intervaly měření.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva hlásí Průměrná velikost fyzické paměti, který právě používá proces v bajtech (pracovní sada). Pracovní sada procesu představuje stránky z adresního prostoru procesu, které jsou aktuálně umístěny ve fyzické paměti.  
  
 Hlášené hodnota obsahuje trvalé stránek ze segmentů sdílené paměti, které proces odkázal. Proces odkazy jsou součástí segmenty sdílené paměti, které se počítají sdílené knihovny DLL. Hodnota pracovní sada procesu může být vyšší než velikost virtuální paměti, který tento proces alokoval z důvodu sdílené paměti segmenty.  
  
 Hlášené hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaným procesem.  
  
 Velikost pracovní sady procesu odráží velikost virtuální paměti proces aktivně používá. Je rovněž ovlivněna množství fyzické paměti (nebo RAM) k dispozici pro spuštění aplikace a kolizí pro tuto fyzickou paměť z jiných spuštěných procesů. Pokud je omezené fyzické paměti, hodnota pracovní sada procesu je výstižný k odlišení výrazně jako operační systémy pokusí vyrovnávat využití paměti ve active procesy pravidelně ořízne poměrně neaktivní stránky z pracovní sady procesu.  
  
 Další informace o sadách pracovní proces najdete v tématu [pracovní sady](http://go.microsoft.com/fwlink/?LinkId=177830) v dokumentaci k Windows Správa paměti z webu MSDN.  
  
## <a name="how-to-use-rule-data"></a>Jak používat Data pravidla  
 Použijte pravidla hodnotu k porovnání výkonu různých verzí nebo sestavení tohoto programu nebo pochopit výkon aplikace v různých scénářích profilování.  
  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [značky zobrazení](../profiling/marks-view.md) zobrazení data profilování. Najít **Process\Working nastavit** a **Paměť\Stránky/s** sloupce. Porovnání dva sloupce a určí, jestli je konkrétní fáze spuštění programu, které se zobrazují přidruženou zvýšení aktivity vstupně-výstupní operace stránkování.