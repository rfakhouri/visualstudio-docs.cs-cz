---
title: "DA0506: Maximum nesdílených bajtů přidělených pro profilovaný proces | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0506
- vs.performance.DA0506
- vs.performance.506
ms.assetid: e9c43554-9a85-4d98-9fa4-3b19986e7b62
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4a624e790a618f923f5a70981fc3fef32809966d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0506-maximum-private-bytes-allocated-for-the-process-being-profiled"></a>DA0506: Maximum Nesdílených bajtů přidělených pro profilovaný Proces
|||  
|-|-|  
|Id pravidla|DA0506|  
|Kategorie|Sledování prostředků|  
|Metoda profilace|Všechny|  
|Zpráva|Tyto informace byly získány pouze pro informaci. Čítač soukromých bajtů procesu měří virtuální paměti přidělené procesu, který se profilace. Hodnota hlášené, přes všechny intervaly měření pozorovanou maximální.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva znamená, maximální velikost virtuální paměti, který tento proces alokoval aktuálně v bajtech (nesdílených bajtů). Nesdílených bajtů představuje umístění virtuální paměti, které byly přiděleny proces, který lze přistupovat pouze vláken běžících v rámci procesu.  
  
 Pro 32bitové procesů spuštěných na 32bitový počítač horní limit počtu soukromá část adresní prostor procesu je 2 GB. Pomocí [3 GB](http://go.microsoft.com/fwlink/?LinkId=177831) přepínač Boot.ini 32bitovými procesy můžete získat až 3 GB virtuální paměti. 32bitový proces, který běží na 64bitový počítač můžete získat až 4 GB privátní virtuální paměti.  
  
 64bitová verze procesu, který je spuštěn na 64bitový počítač můžete získat až 8 TB privátní virtuální paměti.  
  
 Maximální hodnotu hlášenou je přes všechny intervaly měření, ve kterých byl aktivní profilovaným procesem.  
  
 Další informace o procesu adresní prostory, najdete v části [virtuální adresní prostor](http://go.microsoft.com/fwlink/?LinkId=177832) v dokumentaci k Windows Správa paměti.  
  
## <a name="how-to-use-rule-data"></a>Jak používat Data pravidla  
 Použijte hlášené hodnotu k porovnání výkonu různých verzí nebo sestavení tohoto programu nebo pochopit výkon aplikace v různých scénářích profilování.  
  
 Maximální hodnota nesdílených bajtů procesu, že se blíží architektury limit jak velký adresní prostor procesu můžou růst může vést k mimo paměti výjimky. Další informace najdete v tématu [příčin problémů s pamětí](http://go.microsoft.com/fwlink/?LinkID=177833) v časopise MSDN.