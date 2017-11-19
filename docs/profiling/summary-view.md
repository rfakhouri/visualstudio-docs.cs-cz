---
title: "Souhrnné zobrazení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.summary
helpviewer_keywords:
- performance reports, summary view
- profiling tools reports, Summary view
- profiling tools, Summary view
- Summary view
ms.assetid: 98a1eb71-bbf5-4ce7-8559-cdc29f082c4b
caps.latest.revision: "37"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f07b924c5af117f39e19dc5add6046a14be22a6b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="summary-view"></a>Souhrnné zobrazení
Souhrnné zobrazení zobrazí informace o výkonu nejnákladnější funkce nebo objekty v profilaci spustit. Toto zobrazení nabízí časová osa grafu a minimálně dva seznamy nejnákladnější funkce nebo objekty podle metriky výkonu profilování metody. Data v tomto zobrazení, závisí na profilování metoda, která byla použita (vzorkování, instrumentace nebo souběžnosti) a jestli byl shromážděn přidělení paměti .NET.  
  
 Pro všechny souhrnné zobrazení s výjimkou souhrnné zobrazení dat souběžnosti zobrazuje časová osa grafu v zobrazení souhrnu využití procesoru (CPU) PROFILOVANÉHO aplikace v průběhu času, který profilace došlo k chybě.  
  
-   Pokud zadáte segment čas v grafu, můžete opakovat analýzu dat pro tento segment nebo zvětšení zobrazení časové osy segment, který jste zadali. Další informace najdete v tématu [postupy: filtrování zobrazení sestav ze souhrnné časové osy](../profiling/how-to-filter-report-views-from-the-summary-timeline.md)  
  
-   Můžete kliknout na funkci v seznamu zobrazení se souhrnnými informacemi k otevření zobrazení podrobností funkce pro funkci. Můžete také můžete kliknout pravým tlačítkem funkce pro další možnosti zobrazení.  
  
-   Chcete-li upravit počet položek, které se zobrazují v zobrazení se souhrnnými informacemi seznamy, otevřete **nástroje** nabídky, přejděte na příkaz **možnosti**a potom klikněte na **nástroje pro sledování výkonu**. V části **obecné nastavení**, změnit **počet funkcí v zobrazení se souhrnnými informacemi** nastavení.  
  
## <a name="notifications-links"></a>Oznámení odkazy  
 Můžete kliknout na odkazy v seznamu oznámení a nastavit možnosti zobrazení sestavy. V seznamu je pravé ose grafu.  
  
|||  
|-|-|  
|**Zobrazit bez uživatelského kódu**<br /><br /> **Zobrazit pouze můj kód**|Není dostupné pro nativní kód nebo profilace data, která nebyla shromážděna pomocí metody instrumentace. Přepíná mezi zobrazením jenom data z uživatelského kódu (**zobrazit pouze můj kód**) a zobrazení dat ze všech kód, včetně systému kódu (**zobrazit kód Neuživatelských**). Ve výchozím nastavení je omezený na uživatelský kód data. Chcete-li změnit nastavení, [postupy: filtrování profilace nástroje pro zobrazení sestav k zobrazení pouze můj kód](../profiling/how-to-filter-profiling-tools-report-views-to-display-just-my-code.md).|  
|**Pokyny pro zobrazení**|Zobrazí upozornění pravidlo výkonu v **seznam chyb** okno. Další informace najdete v tématu [použití pravidel výkonu k analýze dat](../profiling/using-performance-rules-to-analyze-data.md)|  
  
## <a name="report"></a>Sestava  
 Můžete kliknout na odkazy v seznamu sestav, chcete-li otevřít jiné zobrazení a chcete porovnat, uložit nebo sestavu filtrovat. V seznamu je pravé ose grafu.  
  
|||  
|-|-|  
|**Zobrazení stromu volání oříznutý**|Zobrazuje nejnákladnější cesty provádění v zobrazení stromu volání. Další informace najdete v tématu [zobrazení stromu volání](../profiling/call-tree-view.md).|  
|**Zobrazit aktivní čáry**|Není k dispozici pro profilace data, která nebyla shromážděna pomocí metody instrumentace. Nejnákladnější řádků zdrojového kódu se zobrazí v zobrazení řádků. Další informace najdete v tématu [zobrazení řádků](../profiling/lines-view.md).|  
|**Porovnání sestavy**|Zobrazí **vyberte analysis soubory pro porovnání** dialogové, kde můžete určit jiné profilování datový soubor má být porovnán aktuálního souboru. Další informace najdete v tématu [porovnávání datových souborů výkonu](../profiling/comparing-performance-data-files.md).|  
|**Export dat sestavy**|Zobrazí **exportovat sestavy** dialogové, kde můžete určit jeden nebo více zobrazení sestav uložit jako textový soubor s oddělovači (CSV) nebo soubory XML. Další informace najdete v tématu [postupy: Export sestavy nástrojů pro profilaci](http://msdn.microsoft.com/en-us/174b5bd3-df9b-4fd4-88d4-76032ab90451).|  
|**Analyzovaných sestavu uložit**|Uloží aktuální datového souboru profilování jako .vsps soubor, který otevře rychleji v rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [postupy: uložení analyzovali profilace datové soubory](http://msdn.microsoft.com/en-us/0340ddde-caf4-48ac-8af3-d15dcdade556).|  
|**Filtrování dat sestavy**|Zobrazí profilování podokno filtru sestavy, kde můžete určit kritéria, která omezí data v zobrazení sestavy. Další informace najdete v tématu [filtr zobrazení sestav výkonu](../profiling/performance-report-view-filter.md)|  
|**Přepnout na celou obrazovku**|Přepne režim celé obrazovky pro zobrazení sestavy.|  
  
## <a name="see-also"></a>Viz také  
 [Souhrnné zobrazení](../profiling/summary-view-sampling-data.md)   
 [Souhrnné zobrazení](../profiling/summary-view-instrumentation-data.md)   
 [Souhrnné zobrazení](../profiling/summary-view-dotnet-memory-data.md)