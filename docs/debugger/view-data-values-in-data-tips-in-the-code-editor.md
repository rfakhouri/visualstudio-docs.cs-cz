---
title: "Zobrazení hodnot dat v datatips – v editoru kódu | Microsoft Docs"
ms.custom: 
ms.date: 07/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], DataTips
- DataTips tool
ms.assetid: ffa7bd18-439b-4685-a9b3-c7884b5de41f
caps.latest.revision: "38"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2eb975b5d4c1f3450ca18b1ea0da3cd3b7fb6375
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="view-data-values-in-datatips-in-the-code-editor"></a>Zobrazení hodnot dat v datatips – v editoru kódu
Datatips – poskytují pohodlný způsob, jak zobrazit informace o proměnných v programu během ladění. Datatips – fungovat pouze v režimu pozastavení a pouze s proměnné, které jsou v aktuálním oboru provádění.
  
### <a name="to-display-a-datatip"></a>Chcete-li zobrazit datového tipu  
  
1. Nastavit zarážky a spuštění ladění (stiskněte **F5**).

2. Kde je pozastavená v ladicím programu, umístěte ukazatel myši nad všechny proměnné v aktuálním oboru.
  
     Zobrazí se popis dat.
  
3.  Popis dat zmizí při odebrání ukazatel myši. Pokud chcete připnout popis dat tak, aby zůstane otevřený, klikněte na tlačítko **připnout na zdroj** ikony nebo klikněte pravým tlačítkem na proměnnou, pak klikněte na **připnout na zdroj**.

    ![Připnutí Data Tip](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

    > [!NOTE]
    > Datové typy jsou vždy vyhodnoceny v kontextu, kde k pozastavení a není ukazatele kurzor. Pokud je ukazatel myši nad proměnnou v jiné funkci se stejným názvem jako proměnné, která je v aktuálním kontextu, hodnota proměnné v jiné funkce se zobrazí jako hodnoty proměnné v aktuálním kontextu.
  
### <a name="to-unpin-a-datatip-and-make-it-float"></a>Odepnout popis dat a jeho float  
  
-   V definovaného popis dat, klikněte na **Odepnout ze zdroje** ikonu.  
  
     Na ikonu Připnutí změny Odepnout pozici. Popis dat nyní obtéká výše všechna otevřená okna. Plovoucí popis dat zavře při ukončení relace ladění.  
  
### <a name="to-repin-a-floating-datatip"></a>Chcete-li repin plovoucího datového tipu  
  
-   Popis dat klikněte na ikonu PIN kód.  
  
     Na ikonu Připnutí změny definovaného pozici. Pokud popis dat mimo okno zdroj, na ikonu Připnutí je zakázané a připnout popis dat nedá.  
  
### <a name="to-close-a-datatip"></a>Zavřete datového tipu  
  
-   Umístěte ukazatel myši nad datového tipu a klikněte **Zavřít** ikonu.  
  
### <a name="to-close-all-datatips"></a>Zavřete všechny datatips –  
  
-   Na **ladění** nabídky, klikněte na tlačítko **zrušte všechny datatips –**.  
  
### <a name="to-close-all-datatips-for-a-specific-file"></a>Zavřete všechny datatips – pro konkrétní soubor  
  
-   Na **ladění** nabídky, klikněte na tlačítko **zrušte všechny datatips – připnuli k** *soubor*.  
  
## <a name="expand-and-edit-information"></a>Rozbalte položku a úpravy informací o  
 Datatips – můžete použít k rozšíření pole, do struktury nebo objektu zobrazíte její členy. Můžete taky upravit hodnoty proměnné z datového tipu.  
  
#### <a name="to-expand-a-variable-to-see-its-elements"></a>Chcete-li rozšířit proměnné zobrazíte jejích elementů.  
  
-   V popis dat, umístěte ukazatel myši  **+**  přihlášení, která byla zaslána před název proměnné.  
  
    Proměnná se rozbalí a zobrazí jeho prvky ve formuláři stromu.

    ![Zobrazení dat Tip](../debugger/media/dbg-tour-data-tips.gif "zobrazení dat tipu")
  
    Pokud je proměnná rozbalen, můžete na klávesnici klávesy se šipkami přesunout nahoru a dolů. Alternativně můžete pomocí myši.  
  
#### <a name="to-edit-the-value-of-a-variable-using-a-datatip"></a>Chcete-li upravit hodnoty proměnné pomocí datového tipu  
  
1.  V popis dat klikněte na hodnotu. To je zakázané hodnoty jen pro čtení.  
  
2.  Zadejte novou hodnotu a stiskněte klávesu ENTER.  
  
## <a name="making-a-datatip-transparent"></a>Změna průhledný datového tipu  
 Pokud chcete zobrazit kód, který je za datového tipu, můžete nastavit popis dat dočasně transparentní. To neplatí pro datatips –, které jsou připnuté nebo plovoucí.  
  
#### <a name="to-make-a-datatip-transparent"></a>Chcete-li transparentní datového tipu  
  
-   V popis dat stiskněte klávesu CTRL.  
  
     Popis dat zůstane transparentní, dokud není podržíte stisknutou klávesu CTRL.  
  
## <a name="visualize-complex-data-types"></a>Vizualizace komplexními datovými typy  
 Pokud se vedle názvu proměnné v popis dat, jeden nebo více zobrazuje ikonu lupy [vizualizérech](../debugger/create-custom-visualizers-of-data.md), například [řetězec vizualizérech](../debugger/string-visualizer-dialog-box.md), jsou k dispozici pro proměnné daného datového typu. Vizualizéru můžete použít k zobrazení informací smysluplnější, obvykle grafické způsobem.
  
#### <a name="to-view-the-contents-of-a-variable-using-a-visualizer"></a>Chcete-li zobrazit obsah proměnné pomocí vizualizéru  
  
-   Klikněte na ikonu lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "vizualizér ikonu") a vyberte výchozí vizualizér pro datový typ.  
  
     -nebo-  
  
     Klikněte na rozbalovací šipku vedle vizualizér vyberte ze seznamu příslušnou vizualizérech pro datový typ.  
  
     Vizualizéru zobrazí informace.  
  
## <a name="add-information-to-a-watch-window"></a>Přidání informací do okno kukátka  
 Pokud chcete nadále sledovat proměnnou v zobrazení seznamu, můžete přidat proměnnou **sledovat** okna z datového tipu.  
  
#### <a name="to-add-a-variable-to-the-watch-window"></a>K přidání proměnné do okna kukátka  
  
-   Klikněte pravým tlačítkem popis dat a pak klikněte na tlačítko **Přidat kukátko**.  
  
     Proměnná je přidán do **sledovat** okno. Pokud používáte edici, která podporuje více **sledovat** windows, proměnné se přidá do **kukátko 1.**  
  
## <a name="import-and-export-datatips"></a>Import a export datatips –  
 Datatips – můžete exportovat do souboru XML, který je možné sdílet s kolegy nebo upravovat pomocí textového editoru.  
  
#### <a name="to-export-datatips"></a>Chcete-li exportovat datatips –  
  
1.  V nabídce ladění, klikněte na tlačítko **exportovat datatips –**.  
  
     **Datatips – Export** zobrazí se dialogové okno.  
  
2.  Použijte soubor sady standardů techniky přejděte do umístění, kam chcete uložit soubor XML, zadejte název souboru v **název souboru** pole a pak klikněte na **OK**.  
  
#### <a name="to-import-datatips"></a>Chcete-li importovat datatips –  
  
1.  V nabídce ladění, klikněte na tlačítko **datatips – Import**.  
  
     **Datatips – Import** zobrazí se dialogové okno.  
  
2.  Pomocí dialogového okna se najít soubor XML, který chcete otevřít a klikněte na tlačítko **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Sledování a QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Vytvořit vlastní Vizualizérech](../debugger/create-custom-visualizers-of-data.md)   