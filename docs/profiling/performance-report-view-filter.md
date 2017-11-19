---
title: "Filtr zobrazení sestav výkonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, Profiler Report view filter
- Profiler Report View filter, profiling tools
ms.assetid: 35f89d86-4683-4db1-aa0c-ae0ce65fa524
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8a7bee6cb18fee301dfab5e7c08c58521eac4e84
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="performance-report-view-filter"></a>Filtr zobrazení sestav výkonu
Filtr zobrazení sestav profileru okna se nachází v horní části okna sestavy výkon. Pokud ho nevidíte, klikněte **zobrazit filtru** tlačítko.  
  
 Můžete upravit každou klauzuli filtru upřesňující výsledky. Následující sloupce jsou k dispozici v Tvůrce filtru.  
  
|Filtrovat položky|Popis|  
|-----------------|-----------------|  
|Nebo|Zvolte **a** je-li tuto klauzuli i další klauzule musí být hodnota true pro odpovídat výsledku. Zvolte **nebo** je-li tuto klauzuli nebo další klauzule může být hodnota true pro odpovídat výsledku.|  
|Pole|Vyberte pole, které chcete použít v klauzuli filtru ze seznamu datových polí, které jsou k dispozici v aktuální soubor sestavy.|  
|Operátor|Vyberte operátor, který určuje vztah, který chcete mezi pole a hodnotu.<br /><br /> = Rovno<br /><br /> <> Nerovná se<br /><br /> < Menší než<br /><br /> > Větší než<br /><br /> < = menší než nebo rovno<br /><br /> > = větší než nebo rovno|  
|Hodnota|Vyberte nebo zadejte hodnotu, která má být vyhledán. Některá pole seznamu dostupné hodnoty pro pole.|  
  
 Klauzulí filtru můžete přidat, dokud si myslíte, že filtr získáte nejlepších výsledků. Klikněte na tlačítko **provést filtru** použít filtr datového souboru.  
  
 Z **značky** zobrazení sestavy můžete vygenerovat klauzulí filtru k omezení dat v zobrazení sestav k datům, která se shromažďují mezi dvě značky. Vyberte značky, které chcete začínat a končit sestav dat, klikněte pravým tlačítkem a vyberte buď **přidat filtr na značky** nebo **přidat filtr na časová razítka**. Oba filtry omezení dat v aktuálním datového souboru stejné značky span; **Přidat filtr na značky** lze použít pro další soubory .vsp.  
  
 Uložení se filtr, klikněte na tlačítko **exportovat filtru** na panelu nástrojů Sestava výkonu a pak zadejte umístění a název souboru .vspf. Chcete-li načíst dříve uložený filtr, klikněte na tlačítko **filtr pro Import** a vyhledejte soubor uložený filtr. Filtr souborů mohou také použity k filtrování datových souborů na počítačích, které mají samostatné profilace nástroje nainstalované. Další informace najdete v tématu [vsperfreport –](../profiling/vsperfreport.md).  
  
## <a name="see-also"></a>Viz také  
 [Analýza výkonu nástrojů pro Data](../profiling/analyzing-performance-tools-data.md)   
 [Vsperfreport –](../profiling/vsperfreport.md)