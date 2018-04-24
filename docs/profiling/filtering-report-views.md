---
title: Filtrování zobrazení sestav | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, configuring
ms.assetid: 820cf192-7fd6-4bee-9a51-aa69154aca85
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c613e4b200df0153827fb10013416211a2eb2062
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="filtering-report-views"></a>Filtrování zobrazení sestav
Profilace datových souborů profilování data, která se zobrazí v zobrazení výkon sestav a exportují do souborů sestav omezit, můžete použít filtry. Můžete omezit sestavy pro data mezi hodnot časového razítka a můžete omezit data, která mají konkrétní procesy a vlákna. Můžete uložit filtrů do souboru a pak vytvořit filtr na jiný soubor dat profilování importováním filtr.  
  
 Sestavy pro segment čas můžete také omezit pomocí grafického rozhraní časová osa zobrazení souhrnu. V tématu [postupy: filtrování zobrazení sestav ze souhrnné časové osy](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
 Vyloučit ze sestavy systému a kód třetích stran, najdete v části [postup: Filtr profilace nástroje pro zobrazení sestav k zobrazení pouze můj kód](../profiling/how-to-filter-profiling-tools-report-views-to-display-just-my-code.md)  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-create-a-profiler-report-filter"></a>K vytvoření filtru sestav profileru  
  
1.  Pokud se nezobrazí okno Filtr zobrazení sestav výkonu, klikněte na tlačítko **zobrazit filtru** na panelu nástrojů výkonu zobrazení sestavy.  
  
     Filtr zobrazení sestav výkonu je tabulka. Každý řádek v tabulce představuje klauzuli filtru. Můžete přidat libovolný počet klauzulí jako chcete filtr.  
  
2.  Pro každou klauzuli, který chcete přidat do filtru vyberte nebo zadejte hodnoty do následujících polí řádku.  
  
    |Pole|Popis|  
    |-----------|-----------------|  
    |**Nebo**|Zvolte **a** je-li tuto klauzuli i další klauzule musí být hodnota true pro odpovídat výsledku. Zvolte **nebo** je-li tuto klauzuli nebo další klauzule může být hodnota true pro odpovídat výsledku.|  
    |**Pole**|Vyberte pole sestavy, které chcete použít v klauzuli filtru ze seznamu zobrazených datová pole.|  
    |**Operátor**|Vyberte operátor, který určuje vztah, který chcete v klauzuli mezi pole a hodnotu.<br /><br /> = Rovno<br /><br /> <> Nerovná se<br /><br /> < Menší než<br /><br /> > Větší než<br /><br /> < = menší než nebo rovno<br /><br /> > = větší než nebo rovno|  
    |**Hodnota**|Vyberte nebo zadejte hodnotu, která má být vyhledán. Některá pole seznamu dostupné hodnoty pro pole.|  
  
3.  
  
#### <a name="to-create-a-profiler-report-filter-from-the-marks-report-view"></a>K vytvoření filtru sestav profileru z zobrazení sestavy značky  
  
1.  Vyberte **značky** z **aktuální zobrazení** seznamu na panelu nástrojů výkonu zobrazení sestavy.  
  
     Zobrazí se sestava profileru značky.  
  
2.  Vyberte trasování událostí pro Windows nebo vzorkování i, kterou chcete použít jako výchozí bod sestavy.  
  
3.  Stiskněte a podržte klávesu CTRL a klikněte na událost, která chcete použít jako koncový bod sestavy.  
  
4.  Klikněte pravým tlačítkem a pak klikněte na jednu z následujících možností:  
  
    -   **Přidat filtr na značky** vytvoří klauzulí filtru, které používají sloupec označit jako pole filtru.  
  
    -   **Přidat filtr na časová razítka** vytvoří klauzulí filtru, které používají sloupec časového razítka v milisekundách jako pole filtru.  
  
     Dvě možnosti filtrovat aktuální soubor dat na stejnou počáteční a koncový bod. Buď možnost může být lepší, když exportujete filtr pro použití v jiných sestavách.  
  
#### <a name="to-load-an-existing-filter-from-a-file"></a>Načtení existující filtru ze souboru  
  
1.  Na panelu nástrojů výkonu zobrazení sestavy, klikněte na tlačítko **filtr pro Import**.  
  
     **Zatížení filtru** se zobrazí dialogové okno.  
  
2.  Zadejte umístění a název souboru filtru (.vspf) načíst.  
  
#### <a name="to-execute-a-filter"></a>K provedení filtru  
  
-   Na panelu nástrojů výkonu zobrazení sestavy, klikněte na tlačítko **spustit filtr**.  
  
#### <a name="to-stop-a-filter-that-is-taking-too-long-to-execute"></a>Chcete-li zastavit filtr, který trvá příliš dlouho provést  
  
-   Na panelu nástrojů výkonu zobrazení sestavy, klikněte na tlačítko **zastavit filtru**.  
  
#### <a name="to-remove-a-filter-on-a-report-view"></a>Chcete-li odebrat filtr zobrazení sestav  
  
1.  Odstranění řádků z klauzule v filtr zobrazení sestav výkonu.  
  
2.  Na panelu nástrojů výkonu zobrazení sestavy, klikněte na tlačítko **spustit filtr**.  
  
#### <a name="to-save-a-filter-to-a-file"></a>Uložení filtru do souboru  
  
1.  Na panelu nástrojů výkonu zobrazení sestavy, klikněte na tlačítko **Exportovat filtr**.  
  
     **Uložit filtru** se zobrazí dialogové okno.  
  
2.  Zadejte umístění a název souboru filtru (.vspf) pro uložení.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení sestav nástrojů pro přizpůsobení výkonu](../profiling/customizing-performance-tools-report-views.md)