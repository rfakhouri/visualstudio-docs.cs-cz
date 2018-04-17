---
title: Funkce pracovního postupu návrháře prostředí | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- WFDShellFeatures.UI
ms.assetid: 14bfe312-9592-408e-92ce-e98585ad16e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ecf7d88b6436ba117b85c2ea6cc423520f9fd873
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="workflow-designer-shell-features"></a>Funkce pracovního postupu návrháře prostředí

Návrháři pracovních postupů Windows se skládá ze tří hlavních oblastí uživatelského rozhraní: plochu návrháře, navigačního panelu nad ním a pod ním prostředí. Navigačního panelu, umístěný v horní části obrazovky se používá k zobrazení seznamu nadřazených aktuální kořenové aktivity. Další informace najdete v tématu [postupy: použití navigace](../workflow-designer/how-to-use-breadcrumb-navigation.md). Plochu návrháře umístěný v centru obrazovky se používá k vytváření pracovních postupů. Prostředí, umístěný v dolní části obrazovky, obsahuje řadu tlačítek pro Správa aktuálního zobrazení.

## <a name="shell-features"></a>Funkce prostředí
 Prostředí má tlačítka na pravé straně panelu můžete zvětšit nebo zmenšit pracovní postup, podle obsahu pracovního postupu na velikost obrazovky a zobrazit nebo skrýt mapu přehledu. Také můžete zvětšit nebo zmenšit pracovní postup pomocí klávesové zkratky CTRL ++ a CTRL +-.

## <a name="overview-map"></a>Přehled mapy
 Přehled mapa zobrazuje malé verzi celý aktivity v aktuální kořenové s popisem cesty, včetně všech jejích podřízených a všemi podřízenými rozšířené. Je zobrazení, obdélníku s oranžové ohraničení, který označuje části aktivity zobrazené v editoru. Přetahování rámeček kolem mapu přehledu posune návrháře pracovních postupů a změní zobrazení editoru.

> [!NOTE]
> [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Je virtualizované uživatelské rozhraní. Návrháře aktivit jsou vykreslovány pouze v případě potřeby. Část pracovní postup nebylo nikdy řádně na plochu návrháře, část se zobrazí jako bílé na mapu přehledu. Posouvání kolem mapu přehledu úplně nevykresluje pracovního postupu.

## <a name="copying-or-saving-workflows-as-images"></a>Kopírování nebo uložení pracovních jako obrázky
 Pracovní postupy můžete zkopírovat ve formátu rastrového obrázku nebo uložit ve formátu rastrového obrázku nebo vektoru. Kopírování nebo uložení obrázku poskytuje způsob, jak exportovat zobrazení celý aktivity v aktuální kořenové s popisem cesty, včetně všech jejích podřízených a všemi podřízenými rozšířené na jiném programu.

 Pokud chcete zkopírovat bitovou kopii, klikněte pravým tlačítkem někde v návrháři a vyberte **kopie jako obrázek**. Pokud chcete uložit jako bitovou kopii, klikněte pravým tlačítkem na libovolné místo v návrháři a vyberte **uložit jako obrázek**. Pracovní postupy lze uložit ve formátu JPG, GIF, PNG nebo XPS. Formát je vybrané na **uložit jako** dialogovém okně **uložit jako typ:** rozevírací seznam v dolní části okna.

## <a name="fonts-and-colors"></a>Písma a barev

Písmo použité v [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] uvnitř [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] jsou řízeny písmo prostředí. Barvy zobrazené v [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] změnit, pokud používáte schéma s vysokým kontrastem barvu motivu operačního systému. Je nutné restartovat [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] po provedení změny nastavení písma a barev, než změny se projeví [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)].