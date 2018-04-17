---
title: Navigátor využití | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.performance.utilizationnavigator
ms.assetid: 522a981a-37ef-4cdd-a04c-f1e7525a2aab
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5d970b8d8ddd599c9c8db383cfe46187d6890976
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="utilization-navigator"></a>Navigátor využití
Navigátor využití v Concurrency Visualizer slouží k vyberte časový interval v trasování. Vizualizér souběžnosti znázorňuje využití jader procesoru procesem cíl v průběhu času. To usnadňuje zkontrolujte vzorů využití procesoru a také umožňuje srovnání data o využití a data v ostatních zobrazeních. Navigátor využití se zobrazí v horní části každé zobrazení v vizualizér souběžnosti. Následující obrázek znázorňuje Navigátor využití.  
  
 ![Navigátor využití zobrazující vybraný časový rámec](../profiling/media/cvutilizationnavigator.png "CVUtilizationNavigator")  
Navigátor využití a vybraný časový rámec  
  
 Na obrázku je vybrané interval definované red obdélníku, označuje jako *jezdec*.  
  
 Zde je, jak můžete použít navigátor využití k manipulaci s zobrazené časové rozmezí:  
  
-   Můžete pohybovat přetažením jezdce doleva nebo doprava. (Klávesové: přesunout fokus na úchytu a stiskněte klávesu šipka doleva nebo doprava.)  
  
-   Rozsah interval můžete změnit tak, že přetáhnete jeden z obslužné rutiny pro zpracování. (Klávesové: přesunout fokus na popisovač a stiskněte klávesu šipka vpravo nebo vlevo.)  
  
 Pokud interval můžete změnit pomocí různých řízení přiblížení vizualizér souběžnosti, Navigátor využití aktualizuje, aby odrážely změny.