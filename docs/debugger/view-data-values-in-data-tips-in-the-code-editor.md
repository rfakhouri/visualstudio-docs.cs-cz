---
title: Zobrazení hodnot dat v datových tipech v editoru kódu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 07/14/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: afb318c8aa327345b3cd76ee16b718db1e0386aa
ms.sourcegitcommit: 331dbb12e11fcd7f5d15fab05f3c861e48126e43
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/16/2018
ms.locfileid: "51826734"
---
# <a name="view-data-values-in-datatips-in-the-code-editor"></a>Zobrazení hodnot dat v datových tipech v editoru kódu
DataTips poskytují pohodlný způsob, jak zobrazit informace o proměnných ve svém programu během ladění. DataTips fungovat pouze v režimu pozastavení a pouze s proměnnými, které jsou v aktuálním oboru spuštění. Pokud je to poprvé, kterou jste se pokusili ladění kódu, můžete chtít číst [psali lepší C# kódu pomocí sady Visual Studio](../debugger/write-better-code-with-visual-studio.md) a [ladění pro naprosté začátečníky](../debugger/debugging-absolute-beginners.md) před provedením tohoto článku.
  
### <a name="to-display-a-datatip"></a>Chcete-li zobrazit DataTip  
  
1. Nastavte zarážku a spustit ladění (stisknutím klávesy **F5**).

2. Pokud pozastavení v ladicím programu, umístěte ukazatel myši nad všechny proměnné v aktuálním oboru.
  
     Zobrazí se DataTip.
  
3.  DataTip zmizí při odebrání ukazatel myši. Pro Připnutí DataTip tak, aby zůstane otevřený, klikněte na tlačítko **připojit ke zdroji** ikonu nebo klikněte pravým tlačítkem na proměnnou, pak klikněte na **připojit ke zdroji**.

    ![Připnutí popisu dat.](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

    > [!NOTE]
    > Datových tipech jsou vždy vyhodnoceny v kontextu, kde je spuštění pozastaveno, a ne je ukazatel myši. Pokud je ukazatel myši nad proměnnou v jiné funkce se stejným názvem jako proměnná, která je v aktuálním kontextu, zobrazí se jako hodnotu proměnné v aktuálním kontextu hodnotu proměnné v jiné funkci.
  
### <a name="to-unpin-a-datatip-and-make-it-float"></a>Odepnout DataTip a usnadnit float  
  
-   V připojených DataTip, klikněte **Odepnout ze zdroje** ikonu.  
  
     Ikona Připnutí změní nepřipnuté pozici. DataTip nyní čísel s plovoucí čárkou nad všechna otevřená okna. S plovoucí desetinnou čárkou DataTip ukončí po ukončení relace ladění.  
  
### <a name="to-repin-a-floating-datatip"></a>Chcete-li repin DataTip s plovoucí desetinnou čárkou  
  
-   V datovém tipu klikněte na ikonu připínáčku.  
  
     Ikona Připnutí změní na připojený pozice. Pokud DataTip je mimo okno zdroje, je zakázán ikonu připínáčku a DataTip nedá připnout.  
  
### <a name="to-close-a-datatip"></a>Zavřete DataTip  
  
-   Umístěte ukazatel myši nad DataTip a potom klikněte na tlačítko **Zavřít** ikonu.  
  
### <a name="to-close-all-datatips"></a>Zavřete všechny DataTips  
  
-   Na **ladění** nabídky, klikněte na tlačítko **vymazat všechny DataTips**.  
  
### <a name="to-close-all-datatips-for-a-specific-file"></a>Zavřete všechny DataTips pro konkrétní soubor  
  
-   Na **ladění** nabídky, klikněte na tlačítko **vymazat všechny DataTips připojené k** *souboru*.  
  
## <a name="expand-and-edit-information"></a>Rozbalte a upravit informace  
 Používání tipů DataTips rozbalte pole, struktury nebo objektu pro zobrazení členů. Můžete také upravit hodnotu proměnné z DataTip.  
  
#### <a name="to-expand-a-variable-to-see-its-elements"></a>Chcete-li rozbalit proměnnou zobrazíte jeho prvky  
  
-   V datovém tipu, umístěte ukazatel myši nad **+** znak, který předchází název proměnné.  
  
    Proměnná se rozbalí a zobrazí jeho prvky ve formě stromu.

    ![Zobrazení datového tipu](../debugger/media/dbg-tour-data-tips.gif "zobrazení popisu dat.")
  
    Při rozbalení proměnné můžete použít klávesy se šipkami na klávesnici přesunout nahoru a dolů. Alternativně můžete pomocí myši.  
  
#### <a name="to-edit-the-value-of-a-variable-using-a-datatip"></a>Chcete-li upravit hodnoty proměnné pomocí DataTip  
  
1.  V datovém tipu klikněte na hodnotu. Tato možnost je zakázána pro hodnoty jen pro čtení.  
  
2.  Zadejte novou hodnotu a stiskněte klávesu ENTER.  
  
## <a name="making-a-datatip-transparent"></a>Změna průhledný DataTip  
 Pokud chcete zobrazit kód, který je za DataTip, lze provádět DataTip dočasně transparentní. To se nevztahuje na datových tipech, které jsou připojené nebo s plovoucí desetinnou čárkou.  
  
#### <a name="to-make-a-datatip-transparent"></a>Chcete-li DataTip transparentní  
  
-   V datovém tipu stiskněte klávesu CTRL.  
  
     Za předpokladu, podržte stisknutou klávesu CTRL, zůstanou DataTip transparentní.  
  
## <a name="visualize-complex-data-types"></a>Vizualizujte komplexních datových typů  
 Pokud ikony lupy vedle názvu proměnné v DataTip, jeden nebo více [vizualizéry](../debugger/create-custom-visualizers-of-data.md), například [řetězec vizualizéry](../debugger/string-visualizer-dialog-box.md), jsou k dispozici pro tento datový typ proměnné. Vizualizéru můžete použít k zobrazení informací lépe vystihuje, obvykle grafické způsobem.
  
#### <a name="to-view-the-contents-of-a-variable-using-a-visualizer"></a>Chcete-li zobrazit obsah proměnné pomocí vizualizéru  
  
-   Klikněte na ikonu lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Vizualizéru ikonu") vybrat výchozí vizualizér pro datový typ.  
  
     -nebo-  
  
     Klikněte na rozbalovací šipku vedle vizualizéru vyberte ze seznamu odpovídající vizualizéry datového typu.  
  
     Vizualizéru se zobrazí informace.  
  
## <a name="add-information-to-a-watch-window"></a>Přidání informací do okna kukátka  
 Pokud chcete pokračovat a sledujte proměnnou v zobrazení seznamu, můžete přidat proměnnou **Watch** okna z DataTip.  
  
#### <a name="to-add-a-variable-to-the-watch-window"></a>K přidání proměnné okno kukátka  
  
-   Klikněte pravým tlačítkem na DataTip a potom klikněte na tlačítko **Přidat kukátko**.  
  
     Proměnná se přidá do **Watch** okna. Pokud používáte edici, která podporuje více **Watch** windows, proměnné se přidá do **kukátko 1.**  
  
## <a name="import-and-export-datatips"></a>Importovat a exportovat DataTips  
 Exportovat DataTips do souboru XML, který je možné sdílet s kolegy nebo upravovat pomocí textového editoru.  
  
#### <a name="to-export-datatips"></a>Chcete-li exportovat DataTips  
  
1.  V nabídce ladit, klikněte na tlačítko **exportovat DataTips**.  
  
     **Exportovat DataTips** zobrazí se dialogové okno.  
  
2.  Pomocí standardních souborových postupů, přejděte do umístění, kam chcete uložit soubor XML, zadejte název souboru v **název_souboru** pole a potom klikněte na tlačítko **OK**.  
  
#### <a name="to-import-datatips"></a>Chcete-li importovat datové tipy  
  
1.  V nabídce ladit, klikněte na tlačítko **importovat DataTips**.  
  
     **Importovat DataTips** zobrazí se dialogové okno.  
  
2.  Pomocí dialogového okna Najít soubor XML, který chcete otevřít a klikněte na tlačítko **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Co je ladění?](../debugger/what-is-debugging.md)  
 [Psali lepší C# kódu pomocí sady Visual Studio](../debugger/write-better-code-with-visual-studio.md)  
 [Nejdřív se podívejte na ladění](../debugger/debugger-feature-tour.md) [zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Kukátko a Rychlé kukátko Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Vytváření vlastních vizualizérů](../debugger/create-custom-visualizers-of-data.md)   