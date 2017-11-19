---
title: "Vsperfreport – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command-line tools, VSPerfReporttool
- performance tools, VSPerfReport tool
- profiling tools,VSPerfReport
- VSPerfReport tool
- command line, tools
- instrumentation, VSPerfReporttool
ms.assetid: dbfd8d91-4430-4b82-81b9-97ac61412a6c
caps.latest.revision: "32"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7fceff125460ad5dc9896226458b1c7dddb077a2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="vsperfreport"></a>VSPerfReport
Vsperfreport – nástroj pro příkazový řádek se používá k vytváření sestav pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci profilace datové soubory. Výchozí formát sestavy je soubor .csv.  
  
 Vsperfreport – používá následující syntaxe:  
  
```  
VSPerfReport [/U] vspfilename [/options]  
```  
  
 Všimněte si, že `filename` musí být platný soubor .vsp nebo .vsps.  
  
 Vsperfreport – nástroj příkazového řádku se také používá k porovnání .vsp nebo .vsps soubory. K vygenerování sestavy rozdíl ("rozdílové"), použijte následující syntaxi:  
  
```  
VSPerfReport [/U] /diff vspfilename1 vspfilename2 [/options]  
```  
  
 `vspfilename1 and vspfilename2`musí být platné .vsp nebo .vsps soubory.  
  
## <a name="symbol-files"></a>Soubory symbolů  
 K zobrazení informací o symbolu například názvy funkcí a čísla řádků, vsperfreport – vyžaduje přístup k symbolu (. Soubory PDB) PROFILOVANÉHO součásti a soubory symbolů systému Windows. Další informace najdete v tématu [postupy: určení umístění souboru se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
  
## <a name="general-report-options"></a>Obecná sestava možnosti  
 Následující tabulka popisuje obecné sestavy formátování možnosti a možnosti, které vyberte data, aby byly hlášené.  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**U**|Výstup sestavy a výstup přesměrovaného konzoly jsou zapsány jako kódování Unicode. Musí být první možnost zadat.|  
|**Souhrn:**[*typy*]|Vytvoří jeden nebo více typů sestav.<br /><br /> -   `All`-všechny typy sestav jsou generovány.<br />-   `CallerCallee`-relace nadřazený podřízený mezi funkce.<br />-   `Function`-funkce volána.<br />-   `CallTree`-hierarchie funkce volána.<br />-   `Counter`-hodnoty čítače všechny značky společně s výkon systému Windows.<br />-   `Ip`-profilovaným pokyny.<br />-   `Life`-Doba životnosti přidělené objektů (k dispozici, pokud jsou shromážděná data přidělení.)<br />-   `Line`zdroj dat profilu řádek kódu.<br />-   `Header`-Sestava obsahuje informaci hlavičky souboru.<br />-   `Mark`všechny značky.<br />-   `Module`-profilovaným moduly.<br />-   `Process`-profilovaným procesy.<br />-   `Thread`-profilovaným vláken.<br />-   `Type`-přidělené typy.<br />-   `Contention`-kolizí prostředku.<br />-   `RuleWarnings`-pravidla problémy s výkonem<br />-   `ETW`-všechny události trasování událostí pro Windows (ETW) shromážděné v profilaci spustit. Datový soubor .etl musí být v původním umístění nebo v adresáři, která obsahuje soubor .vsp nebo .vsps.|  
|**XML**|Výstup sestavy ve formátu XML.|  
|**CallTrace**|Vytvoří seznam položku funkce a ukončí, události trasování událostí a značky.|  
|**ClearPackedSymbols**|Odebere dříve vložených symboly z datového souboru profileru. Tento příkaz spustit před spuštěním PackSymbols a sekundu čas.|  
|**Symbolpath –:**`path`|Určuje jeden nebo více cest hledání nebo symbol servery, které obsahují symboly pro datový soubor profileru.|  
|**DebugSymPath**|Uvádí umístění, které jsou vyhledávat symboly a jestli se nacházejí. Tato možnost je užitečná symbol řešení problémů.|  
|**PackSymbols**|Symboly uloží do souboru profilování dat (.vsp), takže nejsou nutné pro analýzu souborů symbolu (.pdb).|  
|**Výstup:** *cesta*&#124; *Název souboru*|Určuje alternativní umístění pro soubory vygenerovanou sestavu. Ve výchozím nastavení sestavy jsou vytvořeny v aktuálním adresáři.|  
|**SummaryFile**|Analýza a uložit soubor souhrnu .vsps analyzovaných informace.|  
|**PrintMarks**|Zobrazte názvy a časová razítka pro všechny značky v souboru zadané sestavy.|  
|**?**|Zobrazí informace o využití.|  
|**NoLogo**|Skryje informace o verzi, po spuštění sestavy.|  
|**UserRulesDirectory**|Určuje adresář obsahující uživatelem definované výkonu pravidla [ještě nebyla implementována].|  
  
## <a name="filter-options"></a>Možnosti filtru.  
 Následující tabulka popisuje možnosti filtrovat všechna dostupná data.  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**JustMyCode**[**:**[`caller`] [,`callee`]]|Zobrazit pouze uživatele volání funkcí aplikace; Skryjte systémová volání.<br /><br /> -Žádné parametry - skrýt všechny funkce systému.<br />-   `caller`-Zobrazit jednu úroveň funkce systému, které volají funkce aplikací.<br />-   `callee`-Zobrazit jednu úroveň systému funkce, které jsou volány funkce aplikací uživatele.|  
|**Čas spuštění:**[*hodnotu*]|Zobrazit pouze data shromážděná po hodnotu (v milisekundách).|  
|**Čas ukončení:**[*hodnotu*]|Zobrazit pouze data shromážděná před hodnotu (v milisekundách).|  
|**FilterFile:**`VSPFFile`|Určuje umístění souboru filtru, který byl vytvořen z okna Sestava výkonu Visual Studio.|  
|**MsFilter:**[*starttime, doba trvání*]|Zobrazit pouze data z `starttime` dokud délka `duration` (v milisekundách).|  
|**Proces:**[*pid*]|Zobrazit pouze data ze zadaného procesu.|  
|**Přístup z více vláken:**[*ID podprocesu*]|Zobrazit pouze data ze zadaného vlákno.|  
|**Přístup z více vláken:**[*ID podprocesu, ID procesu*]|Zobrazit pouze data ze zadaného vlákno přidružené k zadané procesu.|  
  
## <a name="difference-report-options"></a>Rozdíl možností sestav  
 Následující tabulka popisuje možnosti pro porovnávání souborů sestav.  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**Diff**  `vspfile1 vspfile2`|Porovnejte dva soubory (.vsp nebo .vsps) souborů sestav. Souhrn možnosti budou ignorovány pomocí možnosti rozdílové.|  
|**Diff:**[*hodnotu*]|Nižší než tato prahová hodnota rozdílu mezi dvě hodnoty se budou ignorovat. Navíc se nezobrazí nová data s hodnotami pod touto prahovou hodnotou.|  
|**DiffTable:**[*tablename*]|Pomocí této konkrétní tabulky k porovnání souborů. Výchozí hodnota je v tabulce funkce.|  
|**DiffColumn:**[*columnname*]|Použijte tento konkrétní sloupec porovnat hodnoty. Výchozí hodnota je sloupec procent výhradní ukázky.|  
|**QueryDiffTables**|Zobrazí seznam platný tabulky a sloupce pro dva soubory sestav zadali.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení sestav výkonu](../profiling/performance-report-views.md)