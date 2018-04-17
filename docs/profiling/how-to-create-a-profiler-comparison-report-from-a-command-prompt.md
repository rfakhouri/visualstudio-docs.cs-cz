---
title: 'Postupy: vytvoření sestavy porovnání profileru z příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9276578d1dbd8f66e4ed27c0c0fa59004ccaac05
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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