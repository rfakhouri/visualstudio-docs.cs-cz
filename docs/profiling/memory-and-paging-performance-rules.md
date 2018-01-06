---
title: "Paměti a stránkování pravidla výkonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c6466db86c8c27f660fd5a5755f30372efdc7f6c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="memory-and-paging-performance-rules"></a>Pravidla výkonu paměti a stránkování
Pravidla výkonu v paměti a stránkování kategorii identifikovat stránkování aktivity v profilaci spuštění, které může mít vliv na výkon aplikace a odezvy.  
  
|||  
|-|-|  
|[DA0014: Velmi vysoké míry stránkování aktivní paměti na disk](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|Velmi vysoké míry stránkování aktivní paměti na a z disku došlo k chybě v průběhu vytváření profilů spustit. Stránkování sazby na této úrovni obvykle dopad výkon aplikace a odezvy. Zvažte snížení přidělení paměti prostřednictvím revize algoritmy. Budete také muset zvažte požadavky na paměť vaší aplikace. Zkuste spustit znovu profilace na počítači, který má více paměti. Toto pravidlo aktivuje se v případě stránkování aktivity překračuje prahovou hodnotu horní pravidla D0017.|  
|[DA0017: Vysoké míry stránkování aktivní paměti na disk](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Poměrně vysoké míry stránkování aktivní paměti na a z disku došlo k chybě v průběhu vytváření profilů spustit. Stránkování sazby na této úrovni obvykle dopad výkon aplikace a odezvy. Zvažte snížení přidělení paměti prostřednictvím revize algoritmy. Budete také muset zvažte požadavky na paměť vaší aplikace. Zkuste spustit znovu profilace na počítači, který má více paměti.|