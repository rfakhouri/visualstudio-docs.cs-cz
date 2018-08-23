---
title: Pravidla výkonu paměti a stránkování | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e9512fefc13dccebdb0a930ea6000edcbbd8f7a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633440"
---
# <a name="memory-and-paging-performance-rules"></a>Pravidla výkonu paměti a stránkování
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [paměti a stránkování pravidla výkonu](https://docs.microsoft.com/visualstudio/profiling/memory-and-paging-performance-rules).  
  
Pravidla výkonu paměti a stránkování kategorie identifikovat stránkování během spuštění profilování, které můžou ovlivnit výkon aplikace a rychlost odezvy.  
  
|||  
|-|-|  
|[DA0014: Velmi vysoké míry stránkování aktivní paměti na disk](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|K velmi vysokým mírám stránkování aktivní paměti na a z disku došlo k chybě během spuštění profilování. Stránkování sazby na této úrovni obvykle ovlivnit výkon aplikace a rychlost odezvy. Zvažte snížení přidělení paměti prostřednictvím revize algoritmy. Budete také muset zvážit požadavky na paměť vaší aplikace. Zkuste spustit profilaci znovu na počítači, který má více paměti. Toto pravidlo je vyvoláno, když objem stránkování překračuje prahovou hodnotu horní pravidla D0017.|  
|[DA0017: Vysoké míry stránkování aktivní paměti na disk](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Relativně vysoké míry stránkování aktivní paměti na a z disku došlo k chybě během spuštění profilování. Stránkování sazby na této úrovni obvykle ovlivnit výkon aplikace a rychlost odezvy. Zvažte snížení přidělení paměti prostřednictvím revize algoritmy. Budete také muset zvážit požadavky na paměť vaší aplikace. Zkuste spustit profilaci znovu na počítači, který má více paměti.|



