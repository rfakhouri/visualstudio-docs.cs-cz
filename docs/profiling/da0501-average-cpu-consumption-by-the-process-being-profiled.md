---
title: "DA0501: Průměr Spotřeby procesoru profilovaným Procesem. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0501
- vs.performance.DA0501
- vs.performance.501
ms.assetid: b01946b4-75e3-47d5-a1a1-cebfae66a3af
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b17920bea82eff6e71176ff0493faf063d4c2161
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0501-average-cpu-consumption-by-the-process-being-profiled"></a>DA0501: Průměr Spotřeby procesoru profilovaným Procesem.
|||  
|-|-|  
|Id pravidla|DA501|  
|Kategorie|Sledování prostředků|  
|Metoda profilace|Všechny|  
|Zpráva|Průměrné spotřeby procesoru profilovaným procesem.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva hlásí procentuální hodnotu času, který byl procesor zaneprázdněný prováděna pokyny z aplikace. Hlášené hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaným procesem. Hodnota hodnoty může být větší než 100 % na počítači s více než jeden procesor.  
  
## <a name="how-to-use-rule-data"></a>Jak používat Data pravidla  
 Použijte pravidla hodnotu k porovnání výkonu různých verzí nebo sestavení tohoto programu nebo pochopit výkon aplikace v rámci jiného testovacího scénáře.