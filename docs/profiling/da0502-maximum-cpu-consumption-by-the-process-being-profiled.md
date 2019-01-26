---
title: 'DA0502: Maximum spotřeby procesoru profilovaným procesem | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0502
- vs.performance.DA0502
- vs.performance.502
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1a9e2f83bc985423bad8764626be965d29148eed
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923750"
---
# <a name="da0502-maximum-cpu-consumption-by-the-process-being-profiled"></a>DA0502: Maximum spotřeby procesoru profilovaným procesem

|||  
|-|-|  
|Id pravidla|DA0502|  
|Kategorie|Sledování prostředků|  
|Metoda profilace|Všechny|  
|Zpráva|Toto pravidlo je pouze pro informaci. Process()\\Čítač % času procesoru měří využití CPU procesu, který profilujete. Hlášená hodnota je maximum pozorované přes všechny intervaly měření.|  
|Typ pravidla|Informační|  

 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  

## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva znamená maximální procento času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je maximální hodnota uvedená mezi všechny intervaly měření, ve kterých byl aktivní profilovaný proces. Procento, může být větší než 100 % na počítači s více než jeden procesor.  

## <a name="how-to-use-the-rule-data"></a>Jak používat data pravidla  
 Použijte hodnotu pravidla pro porovnání výkonu různých verzí nebo sestavení tohoto programu nebo porozumět výkonu aplikace v různých scénářích profilování.