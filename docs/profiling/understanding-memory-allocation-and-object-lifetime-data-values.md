---
title: "Princip přidělování paměti a životnosti objektů hodnot | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET memory profiling method
- Profiling Tools, .NET memory method
ms.assetid: a22445b3-39a6-4919-8506-2b5b0ceaf77e
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eade1af6d21d4068d96f021d43f60c0ca38bb33c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="understanding-memory-allocation-and-object-lifetime-data-values"></a>Princip přidělování paměti a hodnot životnosti objektů
*Přidělení paměti .NET* profilace metodu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci shromažďuje informace o velikost a počet objektů, které byly vytvořeny v přidělení nebo zničen v uvolnění paměti a další informace o funkci *zásobník volání* kdy k události došlo. A *zásobník volání* je dynamická struktura, která ukládá informace o funkcích, které jsou prováděny na procesor.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 Paměti profileru přerušují procesor počítače při každém přidělení objektu rozhraní .NET Framework v PROFILOVANÉHO aplikace. Při shromažďování dat o době životnosti objektu přerušuje profiler procesor po každém uvolnění paměti rozhraní .NET Framework. Agregovaná data pro jednotlivé funkce PROFILOVANÉHO a pro každý typ objektu.  
  
## <a name="allocation-data"></a>Přidělení dat  
 Při výskytu události .memory, počítá celkového počtu a velikosti paměti přidělené nebo zničení objektů se zvýší.  
  
 Při výskytu události přidělení .memory, profileru zvýší počet ukázka pro jednotlivé funkce v zásobníku volání. Když jsou shromažďována data, jenom jednu funkci v zásobníku volání právě probíhá kód v jeho tělo funkce. Jiných funkcí v zásobníku jsou rodičů v hierarchii volání funkce, které čekají na funkce, které jsou volány vrátit.  
  
-   Pro událost přidělení, profileru zvýší *výhradní* počet funkce, která právě probíhá jeho pokyny vzorků. Protože výhradní ukázka je také součástí celkové (*včetně*) se taky zvýší ukázky funkce, včetně ukázkové počet aktuálně aktivních funkce.  
  
-   Profileru zvýší počet vzorků včetně všech funkcí v zásobníku volání.  
  
## <a name="lifetime-data"></a>Doba platnosti dat  
 Garbage collector v rozhraní .NET Framework spravuje přidělování a uvolňování paměti pro vaši aplikaci. Za účelem optimalizace výkonu systému uvolňování spravovaná halda je rozdělené do tří generací: 0, 1 a 2. Uvolňování paměti Spusťte časové ukládá nové objekty v 0. generace. Objekty, které zůstanou platné i po kolekce jsou povýší a uložené v generace 1 a 2.  
  
 Uvolňování paměti získá podle rušení přidělení celou generování objektů. Doba života objektu zobrazení pro objekty, které PROFILOVANÉHO aplikace vytvořena, zobrazí počet a velikost objekty a generování, když se uvolní.