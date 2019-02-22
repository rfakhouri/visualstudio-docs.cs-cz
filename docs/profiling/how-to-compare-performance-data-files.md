---
title: 'Postupy: Porovnání datových souborů výkonu | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vsperf.choosediffbinaries
helpviewer_keywords:
- profiling tools, how to compare profiler result files
- profiler result files, how to compare
ms.assetid: 1905b45d-c6b3-43c8-87b1-1aee734f37f9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ddbf430358dce0ac57dfe5ef36ff8e8861ea0ef8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56645300"
---
# <a name="how-to-compare-performance-data-files"></a>Postupy: Porovnání datových souborů výkonu
Můžete porovnat výsledky dvou souborů dat profileru jinou (. *Vsp* nebo. *vsps*) tak, že vytvoříte porovnání ("Diff") sestav nebo zobrazení. Srovnání ukazuje rozdíly, regrese výkonu a vylepšení, ke kterým došlo v jedné relaci profilace na druhý.

 Sestava změn představuje zobrazení tabulky dat. V tabulce představuje rozdílů nebo změnit ze standardních hodnot. Tento výpočet určením rozdíl mezi původní hodnoty, základní hodnota a hodnota výsledku z nové analýzy.

 Porovnání dat profiler může být založen na funkce v kódu, moduly v aplikaci, řádky, ukazatele na instrukce (IP) a typy.

 Prahovou hodnotu můžete nastavit ke snížení šumu a vyfiltrovat všechna data v tabulkovém zobrazení řádky, které nebyly změněny o určenou hodnotu.

### <a name="to-create-comparison-file-view-for-a-project-in-performance-explorer"></a>Vytvořit zobrazení souboru porovnání pro projekt v prohlížeči výkonu

1.  V **prohlížeč výkonu**v části **sestavy**, vyberte. *Vsp* nebo. *vsps* soubor sestavy, kterou chcete použít jako hodnoty směrný plán pro porovnání.

2.  Vyberte. *vsp* nebo. *vsps* sestavy soubory, které chcete porovnat.

3.  Klikněte pravým tlačítkem na vybrané soubory a pak klikněte na tlačítko **porovnat sestavy**.

### <a name="to-compare-values"></a>Chcete-li porovnat hodnoty

1.  Vyberte **sestavy porovnání** karta v okně zobrazení sestavy.

2.  V **tabulky** rozevírací seznam, vyberte funkci nebo moduly pro porovnání.

3.  V **sloupec** rozevíracího seznamu vyberte hodnotu, kterou chcete porovnat.

4.  (volitelné) Zadejte hodnotu pro **prahová hodnota**.

5.  Klikněte na tlačítko **Použít**.

### <a name="to-compare-report-files"></a>Chcete-li porovnat soubory sestav

1.  Na **analyzovat** nabídce vyberte možnost **porovnat sestavy výkonu**.

2.  V **vybrat soubory analýzy k porovnání** , procházet a vyberte **referenční soubor** souboru analýzy (. *Vsp* nebo. *vsps*) a **porovnávaný soubor** (. *Vsp* nebo. *vsps*).

3.  Klikněte na **OK**.