---
title: Filtr zobrazení sestav výkonu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profiling tools, Profiler Report view filter
- Profiler Report View filter, profiling tools
ms.assetid: 35f89d86-4683-4db1-aa0c-ae0ce65fa524
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1568ec12a635014239a1533bf00df09a1e63ac14
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668004"
---
# <a name="performance-report-view-filter"></a>Filtr zobrazení sestav výkonu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [filtr zobrazení sestav výkonu](https://docs.microsoft.com/visualstudio/profiling/performance-report-view-filter).  
  
V okně filtru zobrazení sestavy Profiler se nachází v horní části okna sestavy výkonu. Pokud ho nevidíte, klikněte na tlačítko **zobrazit filtr** tlačítko.  
  
 Můžete upravit každou klauzuli filtru pro upřesnění výsledků. Tyto sloupce jsou k dispozici v Tvůrce filtru.  
  
|Filtrovat položky|Popis|  
|-----------------|-----------------|  
|A/nebo|Zvolte **a** Pokud tuto klauzuli i další klauzule musí být hodnota true pro odpovídat výsledek. Zvolte **nebo** Pokud tuto klauzuli nebo další klauzule může být hodnota true pro odpovídat výsledek.|  
|Pole|Vyberte pole pro použití v klauzuli filtru ze seznamu datových polí, které jsou k dispozici v aktuálním souboru sestavy.|  
|Operátor|Vyberte operátor, který určuje vztah, který chcete, aby mezi pole a hodnotu.<br /><br /> = Rovná se<br /><br /> <> Nerovná se<br /><br /> < Menší než<br /><br /> > Větší než<br /><br /> < = menší než nebo rovno<br /><br /> > = je větší než nebo rovno|  
|Hodnota|Vyberte nebo zadejte hledaná hodnota. Některá pole jsou uvedeny dostupné hodnoty pro pole.|  
  
 Klauzulí filtru můžete přidat, dokud si myslíte, že filtr získáte nejlepší výsledky. Klikněte na tlačítko **spustit filtr** použijte filtr do datového souboru.  
  
 Z **značky** zobrazení sestavy můžete vygenerovat klauzulí filtru k omezení dat v zobrazeních sestav o datech, která se shromažďují mezi dvěma značkami. Vyberte značky, které chcete počáteční a koncové sestavy dat, klikněte pravým tlačítkem a vyberte buď **přidat filtr na značky** nebo **přidat filtr na časová razítka**. Oba filtry omezují data v aktuální datový soubor do stejné značky span; **Přidat filtr na značky** lze použít u jiných souborů .vsp.  
  
 Pokud chcete filtr uložit, klikněte na tlačítko **Exportovat filtr** na panelu nástrojů Sestava výkonu a poté zadejte umístění a název souboru .vspf. Chcete-li načíst dříve uložený filtr, klikněte na tlačítko **filtru importu** a vyhledejte soubor uložený filtr. Filtr souborů lze také filtrovat datových souborů na počítačích, které mají samostatné nástroje pro profilaci nainstalované. Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).  
  
## <a name="see-also"></a>Viz také  
 [Analýza výkonu nástrojů pro Data](../profiling/analyzing-performance-tools-data.md)   
 [VSPerfReport](../profiling/vsperfreport.md)



