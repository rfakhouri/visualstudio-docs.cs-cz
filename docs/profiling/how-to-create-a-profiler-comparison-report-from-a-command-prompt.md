---
title: 'Postupy: vytvoření sestavy porovnání profileru z příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5377b9970c488be3f3b37e2834f469dae76f693d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>Postupy: Vytvoření sestavy porovnání profileru z příkazového řádku
Můžete vygenerovat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci sestavy, který porovnává výkonnostní data součásti dvě data profilování (. / Nebo VSP. Soubory VSPS). Sestava zobrazí rozdíly, výkon regresí a vylepšení, které došlo k jedné relace profilování na druhý. Hodnoty v sestavě prezentují rozdílů nebo změna ze směrného plánu první soubor, který určíte. Touto položkou delta je vypočtena určením rozdíl mezi původní hodnoty, což je hodnota směrného plánu, a hodnota výsledek z nové analýzy. Porovnání profileru dat může být založen na funkce v kódu, modulů v aplikaci, řádky, ukazatele na instrukce (IP) a typy.  
  
 Pro zobrazení seznamu identifikátory porovnání kategorií a pole, zadejte následující příkaz:  
  
 **Vsperfreport – /querydifftables***VspFileName1* *VspFileName2*   
  
 Vytvoření sestavy porovnání použijte následující syntaxi:  
  
 **Vsperfreport – / diff** `VspFileName1` *VspFileName2* [**/**`Options`]    
  
 Můžete přidat možnosti z následující tabulce **/vsperfreport – diff** příkazového řádku.  
  
|Možnost|Popis|  
|------------|-----------------|  
|**DiffThreshold:**[*hodnotu*]|Rozdíl ignorujte, pokud je pod tuto procentuální prahová hodnota. Navíc se nezobrazí nová data s hodnotami, které jsou pod touto prahovou hodnotou.|  
|**DiffTable:** *TableName*|Pomocí této tabulky k porovnání souborů. Ve výchozím nastavení se používá tabulce funkce. Zadejte identifikátor, který je uvedený v **vsperfreport – /querydifftables**.|  
|**DiffColumn:** *ColumnName*|Tento sloupec slouží k porovnání hodnot. Ve výchozím nastavení se používá sloupec procent výhradní ukázky. Zadejte identifikátor, který je uvedený v **vsperfreport – /querydifftables**.|