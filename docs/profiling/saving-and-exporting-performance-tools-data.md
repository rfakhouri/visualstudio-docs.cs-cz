---
title: "Ukládání a export výkonu nástrojů pro Data | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: performance tools, saving and exporting reports
ms.assetid: 2e9b28fe-3ed2-4e1d-b9cb-0a5e384380b0
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 37306636da74637cb950ca1502b94a750a51ccba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="saving-and-exporting-performance-tools-data"></a>Ukládání a export výkonu nástrojů pro Data
Toto téma popisuje, jak uložit a exportovat soubory dat výkonu.  
  
##  <a name="BKMK_Save_Profiler_Data_Files_As_Analyzed_Report_Files"></a>Postupy: Uložit jako soubory analyzovaných sestav výkonu datových souborů  
 Můžete uložit filtrované nebo nefiltrované zobrazení profilace soubory dat (.vsp) jako soubory analyzovaných sestav (.vsps). Soubor analyzovaných sestavy můžete zobrazit v okně zobrazení sestavy a je výrazně menší než původní soubor .vsp. Nelze však použít filtr na data .vsps souboru. Můžete vytvořit soubor analyzovaných sestavy z Průzkumníka výkonu bez otevření souboru v integrované vývojové prostředí (IDE), nebo můžete otevřít a filtrovat .vsp soubor a potom uložte výsledky.  
  
#### <a name="to-save-an-analyzed-performance-report-from-the-performance-explorer"></a>Uložení zprávu o analyzovaných výkonu z prohlížeč výkonu  
  
1.  V části **sestavy**, klikněte pravým tlačítkem na profilování datový soubor, který chcete analyzovat a pak klikněte na tlačítko **uložit analyzovali**.  
  
2.  V **uložit analyzovat Data** dialogové okno pole, zadejte adresář a pak zadejte název souboru.  
  
3.  Klikněte na tlačítko **uložit.**  
  
#### <a name="to-save-an-analyzed-performance-report-from-the-report-view-window"></a>Uložit z okna sestavy zobrazit zprávu o analyzovaných výkonu  
  
1.  Otevřete soubor profilování dat (.vsp) v okně zobrazení sestavy.  
  
2.  (Volitelné) Použijte filtr na data. Další informace najdete v tématu [filtr zobrazení sestav výkonu](../profiling/performance-report-view-filter.md).  
  
3.  Klikněte na tlačítko **uložit analyzovali** na panelu nástrojů okna zobrazení sestavy.  
  
4.  V **uložit analyzovat Data** dialogové okno pole, zadejte adresář a pak zadejte název souboru.  
  
5.  Klikněte na tlačítko **uložit.**  
  
## <a name="how-to-export-profiling-tools-reports-to-an-xml-or-csv-file"></a>Postupy: sestav nástrojů pro profilaci exportu. XML nebo. Soubor CSV  
 Jedno nebo více zobrazení sestavy můžete exportovat ze souboru .vsp nebo .vsps datového souboru profilování jako buď čárkami oddělený nebo soubor XML. Data v okně zobrazení sestavy můžete filtrovat, před exportem nebo můžete exportovat zobrazení sestav celého datového souboru z **prohlížeč výkonu** okno.  
  
> [!NOTE]
>  Můžete také zkopírovat a vložit vybrané řádky z okna zobrazení sestavy jako hodnot oddělených tabulátory.  
  
#### <a name="to-export-performance-reports-from-the-performance-explorer-window"></a>Export sestavy pro zvýšení výkonu ze okno Prohlížeč výkonu  
  
1.  V **prohlížeč výkonu**, vyberte sestavu a pak klikněte pravým tlačítkem a vyberte **exportovat**.  
  
     **Exportovat sestavy** zobrazí se dialogové okno.  
  
2.  Vyberte zobrazení sestav, který chcete exportovat.  
  
3.  V části **předpony zprávu s**, zadejte předponu, kterou chcete přidat k názvu sestavy.  
  
4.  V části **exportovat umístění sestavy**, zadejte adresář.  
  
5.  V části **formátu exportované sestavy**, vyberte (oddělený čárkou) (\*.csv\), nebo XML Data (\*.xml\).  
  
6.  Klikněte na tlačítko **exportovat**.  
  
     Každé zobrazení sestavy je uloženo do samostatného souboru, který je pojmenován \<předpony > _\<název zobrazení sestavy >.\< CSV &#124; xml >  
  
#### <a name="to-export-performance-reports-from-the-report-view-window"></a>Export sestavy pro zvýšení výkonu v okně zobrazení sestavy  
  
1.  Otevřete soubor .vsp v okně zobrazení sestavy.  
  
2.  (Volitelné) Použijte filtr na data. Další informace najdete v tématu [filtr zobrazení sestav výkonu](../profiling/performance-report-view-filter.md).  
  
3.  Klikněte na tlačítko **exportovat sestavy** na panelu nástrojů okna zobrazení sestavy.  
  
4.  Vyberte zobrazení sestav, který chcete exportovat.  
  
5.  V části **předpony zprávu s**, zadejte předponu, kterou chcete přidat k názvu sestavy.  
  
6.  V části **exportovat umístění sestavy**, zadejte adresář.  
  
7.  V části **formátu exportované sestavy**, vyberte (oddělený čárkou) (\*.csv), nebo XML Data (\*.xml).  
  
8.  Klikněte na tlačítko **exportovat**.  
  
     Každé zobrazení sestavy je uloženo do samostatného souboru, který je pojmenován \<předpony > _\<název zobrazení sestavy >.\< CSV &#124; xml >  
  
## <a name="see-also"></a>Viz také  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)   
 [Analýza výkonu nástrojů pro Data](../profiling/analyzing-performance-tools-data.md)   
 [Porovnávání souborů dat výkonu](../profiling/comparing-performance-data-files.md)   
 [VSPerfReport](../profiling/vsperfreport.md)
