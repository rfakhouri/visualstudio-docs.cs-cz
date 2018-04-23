---
title: Zobrazení knihovny DLL a spustitelné soubory v ladicím programu | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.modules
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, Modules window
- Modules window
- executable files, displaying while debugging
- debugging [Visual Studio], displaying modules
- DLLs, displaying while debugging
- modules, displaying
ms.assetid: d840fdca-b035-4452-b652-72580c831896
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46dc913b95396e16f208611bcfc926378609bef6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="view-dlls-and-executables-using-the-modules-window-in-the-visual-studio-debugger"></a>Zobrazení knihovny DLL a spustitelné soubory pomocí okna moduly v ladicí program Visual Studio
 
**Moduly** okno zobrazuje seznam knihoven DLL a spustitelné soubory (EXE), které se používají váš program a uvádí relevantní informace pro každý. 

> [!NOTE]
>  Tato funkce není k dispozici pro SQL nebo ladění skriptů. 
  
### <a name="to-display-the-modules-window"></a>Pro zobrazení okna moduly  
  
-   Při ladění, vyberte **ladění > Windows** a pak klikněte na **moduly**.  
  
     Ve výchozím nastavení **moduly** okno seřadí podle zatížení pořadí modulů. Můžete však řadit podle žádné sloupce.  
  
### <a name="to-sort-by-any-column"></a>Seřadit podle kteréhokoli sloupce  
  
-   Klikněte na tlačítko v horní části sloupce.  
  
     Můžete načíst symboly nebo zadejte cestu symbol z **moduly** okno pomocí místní nabídky.  
  
## <a name="loading-symbols"></a>Načítání symboly  
 V **moduly** okně uvidíte, jaké moduly mají načíst symboly ladění. Tato informace se zobrazí v **Symbol stav** sloupce. Pokud je uveden stav **loadingCannot vynecháno najít nebo otevřít soubor PDB**, nebo **načítání zakázané nastavením zahrnutí a vyloučení**, nasměrujete ladicí program ke stažení z je symbol Microsoft veřejné symboly servery nebo načíst symboly z adresáře symbol ve vašem počítači. Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols-manually"></a>Chcete-li ručně načíst symboly  
  
1.  V **moduly** okna, klikněte pravým tlačítkem a modulu, pro kterou nebyly načteny symboly.  
  
2.  Přejděte na příkaz **zatížení symboly z** a pak klikněte na **servery symbolů Microsoft** nebo **Symbol cesta**.  
  
#### <a name="to-change-symbol-load-settings"></a>Chcete-li změnit nastavení načítání – symbol  
  
1.  V **moduly** okna, klikněte pravým tlačítkem na libovolný modul.  
  
2.  Klikněte na tlačítko **symbolů nastavení**.  
  
     Nyní můžete měnit nastavení zatížení symbol, jak je popsáno v [zadejte umístění symbolů a načítání chování](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior). Změny se projeví až po restartování relaci ladění.  
  
#### <a name="to-change-symbol-load-behavior-for-a-specific-module"></a>Chcete-li změnit chování zatížení symbol pro konkrétního modulu  
  
1.  V **moduly** okna, klikněte pravým tlačítkem na modul.  
  
2.  Přejděte na příkaz **nastavení automatického zatížení Symbol** a pak klikněte na **vždy zatížení ručně** nebo **výchozí**. Změny se projeví až po restartování relaci ladění.  
  
## <a name="see-also"></a>Viz také  
 [Pozastavení provádění](http://msdn.microsoft.com/en-us/30fc4643-f337-4651-b1ff-f2de2c098d40)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)