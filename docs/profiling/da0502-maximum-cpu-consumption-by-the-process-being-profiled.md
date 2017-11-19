---
title: "DA0502: Maximum spotřeby procesoru profilovaným procesem | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0502
- vs.performance.DA0502
- vs.performance.502
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d1cd5fbe91b125c00fe617f03711ea52cdf458f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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