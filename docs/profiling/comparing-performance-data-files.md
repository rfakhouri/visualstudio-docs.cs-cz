---
title: Porovnání datových souborů výkonu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, comparing profiling tools report files
- profiling tools reports, comparing
ms.assetid: e6fda144-f21d-4912-9d16-1b8d3555a210
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9802bc92a857192ce144432114a8add2c1becba8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640360"
---
# <a name="compare-performance-data-files"></a>Porovnání datových souborů výkonu

Profilace funkci porovnání souborů dat nástroje vám umožní vybrat dva soubory sestav (. *Vsp* nebo. *vsps*) soubory a generovat sestavy, která ukazuje rozdíly, regrese výkonu a vylepšení, ke kterým došlo v jedné relaci profilace na druhý.

Sestava porovnání datových souborů z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů pro profilaci sady porovnává výsledky analýzy v jeden soubor dat profilování pro výsledky analýzy standardních hodnot v jiném datovém souboru služby. Oba soubory dat musí být vygenerováno stejným způsobem, profilace. Sestava analyzované porovnání se ukládá jako. *vsps* souboru.

Zobrazení sestav porovnání představuje zobrazení tabulky změněná data. V tabulce představuje rozdílů nebo změnit ze standardních hodnot. Delta se počítá tak, že určíte rozdíl mezi původní hodnoty, základní hodnota a hodnota výsledku z nové analýzy.

Porovnání dat profiler může být založen na funkce v kódu, moduly v aplikaci, řádky, ukazatele na instrukce (IP) a typy.

Data profilace, která je k dispozici pro porovnání obsahuje informace, které se zobrazí ve sloupci. Definice tyto názvy sloupců, naleznete v tématu [zobrazení sestav výkonu](../profiling/performance-report-views.md).

Prahovou hodnotu můžete nastavit ke snížení šumu a vyfiltrovat všechna data v zobrazení tabulky porovnání řádků, které nebyly změněny o určenou hodnotu.

## <a name="in-this-section"></a>V tomto oddílu

[Postupy: Porovnání datových souborů výkonu](../profiling/how-to-compare-performance-data-files.md)