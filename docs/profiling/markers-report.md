---
title: "Sestava značek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.report.markers
ms.assetid: 829ce099-172e-4c7e-bbd0-578b110c59bd
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e38aa2f9081c1d362d1125838bcfc2e39bb7f277
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="markers-report"></a>Sestava značek
Sestava značek obsahuje seznam značek v zobrazených časovém intervalu.  Posouvání přiblížení a oddálení nebo skrytí pruhů, může způsobit značek zobrazí nebo zmizí. Sestava obsahuje tyto informace o každé značky:  
  
-   Čas ho zahájení, relativně k začátku trasování.  
  
-   Jeho trvání. Doba trvání je nulová pro příznaky a zprávy, protože představují pro rychlé.  
  
-   ID vlákna, která ji vygenerovala.  
  
-   Zprostředkovatel událostí sledování pro Windows (ETW), který ji vygenerovala.  
  
-   Řada značky, ze kterého byla zapsána.  
  
-   Kategorie události, které patří do.  
  
-   Úroveň jeho význam.  
  
-   Typ (rozpětí, příznak nebo zprávy).  
  
-   Podrobný popis co reprezentuje  
  
 Vyberte **exportovat** tlačítko pro uložení sestavy značek jako soubor CSV. Data můžete použít v souboru CSV s jinými aplikace nebo nástroje.  
  
> [!NOTE]
>  Sestava značek můžete zobrazit 1000 značek. Úplné sestavu zobrazíte všechny značky, můžete exportujte do souboru CSV.