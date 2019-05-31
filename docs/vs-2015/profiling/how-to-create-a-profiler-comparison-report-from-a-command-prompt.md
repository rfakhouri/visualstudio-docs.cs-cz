---
title: 'Postupy: Vytvoření sestavy porovnání Profiler z příkazového řádku | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8c6dabbae5f2d3758aebe0562f99767ee6993d80
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54756736"
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>Postupy: Vytvoření sestavy porovnání Profiler z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete generovat [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů pro profilaci sady sestav, který porovnává data o výkonu ze dvou dat profilování (. VSP nebo. Soubory VSPS). Sestava ukazuje rozdíly, regrese výkonu a vylepšení, ke kterým došlo v jedné relaci profilace na druhý. Hodnoty v sestavě obsahují rozdílů nebo změny, od základních hodnot v prvním souboru, který určíte. Touto položkou delta se počítá tak, že určíte rozdíl mezi původní hodnotu, která je základní hodnota a hodnota výsledku z nové analýzy. Porovnání dat profiler může být založen na funkce v kódu, moduly v aplikaci, řádky, ukazatele na instrukce (IP) a typy.  
  
 Pro výčet identifikátorů porovnání kategorií a pole, zadejte na příkazovém řádku následující:  
  
 **VSPerfReport/querydifftables***VspFileName1*  *VspFileName2*  
  
 Použijte následující syntaxi pro vytvoření sestavy porovnání:  
  
 **VSPerfReport /diff**  `VspFileName1` *VspFileName2* [ **/** `Options`]  
  
 Z následující tabulky můžete přidat možnosti **VSPerfReport/diff** příkazového řádku.  
  
|Možnost|Popis|  
|------------|-----------------|  
|**DiffThreshold:** [*hodnotu*]|Rozdíl ignorujte, pokud byl pod tuto procentuální prahovou hodnotu. Také se nezobrazí nová data s hodnotami, které jsou pod touto prahovou hodnotou.|  
|**DiffTable:** *TableName*|Pomocí této tabulce můžete porovnat soubory. Ve výchozím nastavení se používá tabulka funkcí. Zadejte identifikátor, který je uveden v **VSPerfReport/querydifftables**.|  
|**DiffColumn:** *Názevsloupce*|Tento sloupec slouží k porovnání hodnoty. Ve výchozím nastavení se používá sloupec procent výhradních vzorků. Zadejte identifikátor, který je uveden v **VSPerfReport/querydifftables**.|
