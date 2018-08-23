---
title: 'DA0505: Průměr nesdílených bajtů přidělených pro profilovaný proces | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.DA0505
- vs.performance.rules.DA0505
- vs.performance.505
ms.assetid: 32c612ea-d077-44ba-8e6f-3a96333bad00
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab4ff02bfe8bfacaabddd9204c677544e4fd83a2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633739"
---
# <a name="da0505-average-private-bytes-allocated-for-the-process-being-profiled"></a>DA0505: Průměr Nesdílených bajtů přidělených pro profilovaný Proces
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [DA0505: průměr nesdílených bajtů přidělených pro profilovaný proces](https://docs.microsoft.com/visualstudio/profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled).  
  
Id pravidla | DA0505 |  
| Kategorie | Správa prostředků |  
| Metoda profilace | Všechny |  
| Zpráva | Tato informace byla shromážděna pouze pro informaci. Čítač nesdílených bajtů procesu měří virtuální paměť přidělené procesem, který profilujete. Hlášená hodnota je průměr vypočítaný přes všechny intervaly měření. |  
| Typ pravidla | Informace |  
  
 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva znamená Průměrná velikost virtuální paměti, který má proces nyní přidělenu v bajtech (Nesdílené bajty). Nesdílené bajty představuje virtuální paměti umístění, které byly přiděleny procesem, který je přístupný pouze tím, že běží uvnitř procesu vlákna.  
  
 Pro 32bitové procesy spuštěné na počítači 32bitové horní limit části privátní adresní prostor procesu je 2 GB. Použití [3 GB](http://go.microsoft.com/fwlink/?LinkId=177831) přepínač Boot.ini 32bitové procesy můžete získat až 3 GB virtuální paměti. 32bitový proces, který běží na 64bitovém počítači můžete získat až 4 GB přidělené virtuální paměti.  
  
 64bitový proces, který běží na 64bitovém počítači můžete získat až do 8 TB privátní virtuální paměti.  
  
 Hlášená hodnota je průměr přes všechny intervaly měření, ve kterých byl aktivní profilovaný proces.  
  
 Další informace o procesu adresních prostorů, naleznete v tématu [virtuální adresní prostor](http://go.microsoft.com/fwlink/?LinkId=177832) v dokumentaci k Windows správy paměti.  
  
## <a name="how-to-use-rule-data"></a>Jak používat Data pravidla  
 Použijte hlášená hodnota k porovnání výkonu různých verzí nebo sestavení programu a porozumět výkonu aplikace v různých scénářích profilování.



