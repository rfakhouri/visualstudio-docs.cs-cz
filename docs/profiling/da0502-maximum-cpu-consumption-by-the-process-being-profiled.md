---
title: 'DA0502: Maximum spotřeby procesoru profilovaným procesem | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0502
- vs.performance.DA0502
- vs.performance.502
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 38a3474a481948af19b4a37db3fc3a926565dc73
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="da0502-maximum-cpu-consumption-by-the-process-being-profiled"></a>DA0502: Maximum Spotřeby procesoru profilovaným Procesem
|||  
|-|-|  
|Id pravidla|DA0502|  
|Kategorie|Sledování prostředků|  
|Metoda profilace|Všechny|  
|Zpráva|Toto pravidlo je pouze pro informaci. Process()\\spotřeby procesoru procesu, který se profilace měří Čítač % času procesoru. Hodnota hlášené, přes všechny intervaly měření pozorovanou maximální.|  
|Typ pravidla|Informační|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva hlásí maximální procento času, který byl procesor zaneprázdněný prováděna pokyny z aplikace. Hlášené hodnota je maximální hodnotu hlášenou mezi všechny měření intervaly, ve kterých byl aktivní profilovaným procesem. Procento může být větší než 100 % na počítači s více než jeden procesor.  
  
## <a name="how-to-use-the-rule-data"></a>Jak používat Data pravidla  
 Použijte pravidla hodnotu k porovnání výkonu různých verzí nebo sestavení tohoto programu nebo pochopit výkon aplikace v různých scénářích profilování.