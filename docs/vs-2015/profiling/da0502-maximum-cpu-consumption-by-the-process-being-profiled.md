---
title: 'DA0502: Maximum spotřeby procesoru profilovaným procesem | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DA0502
- vs.performance.DA0502
- vs.performance.502
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a47a9c5964ccf15d2c609233eb600f39bc3ad2d1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54787352"
---
# <a name="da0502-maximum-cpu-consumption-by-the-process-being-profiled"></a>DA0502: Maximum spotřeby procesoru profilovaným procesem
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id pravidla | DA0502 |  
| Kategorie | Sledování prostředků |  
| Metoda profilace | Všechny |  
| Zpráva | Toto pravidlo je pouze pro informaci. Process()\\Čítač % času procesoru měří využití CPU procesu, který profilujete. Hlášená hodnota je maximum pozorované přes všechny intervaly měření. |  
| Typ pravidla | Informační |  
  
 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva znamená maximální procento času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je maximální hodnota uvedená mezi všechny intervaly měření, ve kterých byl aktivní profilovaný proces. Procento, může být větší než 100 % na počítači s více než jeden procesor.  
  
## <a name="how-to-use-the-rule-data"></a>Jak používat Data pravidla  
 Použijte hodnotu pravidla pro porovnání výkonu různých verzí nebo sestavení tohoto programu nebo porozumět výkonu aplikace v různých scénářích profilování.
