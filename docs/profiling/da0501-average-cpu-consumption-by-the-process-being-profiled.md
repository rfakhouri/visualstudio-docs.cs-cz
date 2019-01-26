---
title: 'DA0501: Průměr spotřeby procesoru profilovaným procesem. | Dokumenty Microsoft'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0501
- vs.performance.DA0501
- vs.performance.501
ms.assetid: b01946b4-75e3-47d5-a1a1-cebfae66a3af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b7bd27ceb83105a9d790937b3a5fcb904adf3abd
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54983973"
---
# <a name="da0501-average-cpu-consumption-by-the-process-being-profiled"></a>DA0501: Průměr spotřeby procesoru profilovaným procesem.

|||  
|-|-|  
|Id pravidla|DA501|  
|Kategorie|Sledování prostředků|  
|Metoda profilace|Všechny|  
|Zpráva|Průměr spotřeby procesoru profilovaným procesem.|  
|Typ pravidla|Informace o|  

 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  

## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva znamená procentuální hodnotu času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaný proces. Hodnota může být větší než 100 % na počítači s více než jeden procesor.  

## <a name="how-to-use-rule-data"></a>Jak používat data pravidla  
 Hodnota pravidla použijte k porovnání výkonu různých verzí nebo sestavení tohoto programu nebo porozumět výkonu aplikace v rámci různých testovacích scénářů.