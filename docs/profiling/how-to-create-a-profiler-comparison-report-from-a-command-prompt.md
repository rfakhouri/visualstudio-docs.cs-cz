---
title: 'Postupy: Vytvoření sestavy porovnání Profiler z příkazového řádku | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e63e366bbfe29d56ffc61085e986372ac0a9a2f5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53880764"
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>Postupy: Vytvoření sestavy porovnání profileru z příkazového řádku
Můžete generovat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů pro profilaci sady sestav, který porovnává data o výkonu ze dvou dat profilování (. *Vsp* nebo. *vsps*) soubory. Sestava ukazuje rozdíly, regrese výkonu a vylepšení, ke kterým došlo v jedné relaci profilace na druhý. Hodnoty v sestavě obsahují rozdílů nebo změny, od základních hodnot v prvním souboru, který určíte. Touto položkou delta se počítá tak, že určíte rozdíl mezi původní hodnotu, která je základní hodnota a hodnota výsledku z nové analýzy. Porovnání dat profiler může být založen na funkce v kódu, moduly v aplikaci, řádky, ukazatele na instrukce (IP) a typy.  
  
 Pro výčet identifikátorů porovnání kategorií a pole, zadejte na příkazovém řádku následující:  
  
 **VSPerfReport/querydifftables***VspFileName1* *VspFileName2*  
  
 Použijte následující syntaxi pro vytvoření sestavy porovnání:  
  
 **VSPerfReport/diff** `VspFileName1` *VspFileName2* [**/**`Options`]    
  
 Z následující tabulky můžete přidat možnosti **VSPerfReport/diff** příkazového řádku.  
  
|Možnost|Popis|  
|------------|-----------------|  
|**DiffThreshold:**[*hodnotu*]|Rozdíl ignorujte, pokud byl pod tuto procentuální prahovou hodnotu. Také se nezobrazí nová data s hodnotami, které jsou pod touto prahovou hodnotou.|  
|**DiffTable:** *TableName*|Pomocí této tabulce můžete porovnat soubory. Ve výchozím nastavení se používá tabulka funkcí. Zadejte identifikátor, který je uveden v **VSPerfReport/querydifftables**.|  
|**DiffColumn:** *Názevsloupce*|Tento sloupec slouží k porovnání hodnoty. Ve výchozím nastavení se používá sloupec procent výhradních vzorků. Zadejte identifikátor, který je uveden v **VSPerfReport/querydifftables**.|