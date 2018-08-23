---
title: Sestava značek | Dokumentace Microsoftu
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
- vs.cv.threads.report.markers
ms.assetid: 829ce099-172e-4c7e-bbd0-578b110c59bd
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c8a495135a0a7cf493dfc8a8c407409c37e273e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42665909"
---
# <a name="markers-report"></a>Sestava značek
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [sestava značek](https://docs.microsoft.com/visualstudio/profiling/markers-report).  
  
Značky sestava obsahuje seznam značek v zobrazený časový rámec.  Posouvání nebo změna měřítka zobrazení nebo skrytí procesu, může způsobit, že značky se zobrazí nebo zmizí. Sestava obsahuje informace o jednotlivých značky:  
  
-   Čas, kdy je relativní vzhledem k začátku trasování začal.  
  
-   Vlastnost duration. Doba trvání je nula, příznaky a zprávy, protože představují okamžiku.  
  
-   ID podprocesu, který provedl vygenerování.  
  
-   Zprostředkovatel událostí sledování pro Windows (ETW), který provedl vygenerování.  
  
-   Řada značky, odkud byla zapsána.  
  
-   Kategorie události, které patří.  
  
-   Jeho úroveň důležitosti.  
  
-   Jeho typ (značka span, příznak nebo zprávy).  
  
-   Podrobný popis co představuje  
  
 Zvolte **exportovat** tlačítko pro uložení sestavy značky jako soubor CSV. Data můžete použít v souboru CSV s jinými aplikacemi nebo nástroje.  
  
> [!NOTE]
>  Sestava značek můžete zobrazit značky 1 000. Pokud chcete zobrazit všechny značky, exportujte do souboru CSV úplnou sestavu.



