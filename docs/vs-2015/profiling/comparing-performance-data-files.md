---
title: Porovnání datových souborů výkonu | Dokumentace Microsoftu
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
- profiling tools, comparing profiling tools report files
- profiling tools reports, comparing
ms.assetid: e6fda144-f21d-4912-9d16-1b8d3555a210
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd1c93942282c8a5cb3baf9fdf007a0ba55e3ebe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683352"
---
# <a name="comparing-performance-data-files"></a>Porovnání datových souborů výkonu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [porovnávání datových souborů výkonu](https://docs.microsoft.com/visualstudio/profiling/comparing-performance-data-files).  
  
Profilace funkci porovnání souborů dat nástroje vám umožní vybrat dva soubory sestav (. VSP nebo. VSPS) soubory a generovat sestavy, která ukazuje rozdíly, regrese výkonu a vylepšení, ke kterým došlo v jedné relaci profilace na druhý.  
  
 Sestava porovnání datových souborů z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů pro profilaci sady porovnává výsledky analýzy v jeden soubor dat profilování pro výsledky analýzy standardních hodnot v jiném datovém souboru služby. Oba soubory dat musí být vygenerováno stejným způsobem, profilace. Zprávy analyzované porovnání je uložen jako soubor .vsps.  
  
 Zobrazení sestav porovnání představuje zobrazení tabulky změněná data. V tabulce představuje rozdílů nebo změnit ze standardních hodnot. Delta se počítá tak, že určíte rozdíl mezi původní hodnoty, základní hodnota a hodnota výsledku z nové analýzy.  
  
 Porovnání dat profiler může být založen na funkce v kódu, moduly v aplikaci, řádky, ukazatele na instrukce (IP) a typy.  
  
 Data profilace, která je k dispozici pro porovnání obsahuje informace, které se zobrazí ve sloupci. Definice tyto názvy sloupců, naleznete v tématu [zobrazení sestav výkonu](../profiling/performance-report-views.md).  
  
 Prahovou hodnotu můžete nastavit ke snížení šumu a vyfiltrovat všechna data v zobrazení tabulky porovnání řádků, které nebyly změněny o určenou hodnotu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: porovnání datových souborů výkonu](../profiling/how-to-compare-performance-data-files.md)



