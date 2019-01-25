---
title: Sestava značek | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.markers
ms.assetid: 829ce099-172e-4c7e-bbd0-578b110c59bd
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 20e9ece55f1e17c874832f473236dfbae7684c54
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54833849"
---
# <a name="markers-report"></a>Sestava značek
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Značky sestava obsahuje seznam značek v zobrazený časový rámec.  Posouvání nebo změna měřítka zobrazení nebo skrytí procesu, může způsobit, že značky se zobrazí nebo zmizí. Sestava obsahuje informace o jednotlivých značky:  
  
- Čas, kdy je relativní vzhledem k začátku trasování začal.  
  
- Vlastnost duration. Doba trvání je nula, příznaky a zprávy, protože představují okamžiku.  
  
- ID podprocesu, který provedl vygenerování.  
  
- Zprostředkovatel událostí sledování pro Windows (ETW), který provedl vygenerování.  
  
- Řada značky, odkud byla zapsána.  
  
- Kategorie události, které patří.  
  
- Jeho úroveň důležitosti.  
  
- Jeho typ (značka span, příznak nebo zprávy).  
  
- Podrobný popis co představuje  
  
  Zvolte **exportovat** tlačítko pro uložení sestavy značky jako soubor CSV. Data můžete použít v souboru CSV s jinými aplikacemi nebo nástroje.  
  
> [!NOTE]
>  Sestava značek můžete zobrazit značky 1 000. Pokud chcete zobrazit všechny značky, exportujte do souboru CSV úplnou sestavu.
