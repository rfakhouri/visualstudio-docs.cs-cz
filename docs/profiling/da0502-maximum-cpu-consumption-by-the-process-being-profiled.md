---
title: 'DA0502: Maximum spotřeby procesoru profilovaným procesem | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: e7c8a9806a7a0c84b71d247527d1d6eac4c5637e
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766360"
---
# <a name="da0502-maximum-cpu-consumption-by-the-process-being-profiled"></a>DA0502: Maximum spotřeby procesoru profilovaným procesem
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
  
## <a name="how-to-use-the-rule-data"></a>Jak používat data pravidla  
 Použijte pravidla hodnotu k porovnání výkonu různých verzí nebo sestavení tohoto programu nebo pochopit výkon aplikace v různých scénářích profilování.