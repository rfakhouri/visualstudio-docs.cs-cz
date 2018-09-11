---
title: Zobrazení knihovny DLL a spustitelné soubory v ladicím programu | Dokumentace Microsoftu
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
ms.openlocfilehash: f582c435239c83503b179d6bb5e142936a41cb4b
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279008"
---
# <a name="view-dlls-and-executables-using-the-modules-window-in-the-visual-studio-debugger"></a>Zobrazení knihovny DLL a spustitelné soubory pomocí okna modulů v ladicím programu sady Visual Studio
 
**Moduly** okně zobrazí knihovny DLL a spustitelné soubory (EXE), které jsou používané vaším programem a zobrazuje relevantní informace pro každý. 

> [!NOTE]
>  Tato funkce není k dispozici pro SQL nebo ladění skriptů. 
  
### <a name="to-display-the-modules-window"></a>Chcete-li zobrazit okno moduly  
  
-   Při ladění, vyberte **ladit > Windows** a potom klikněte na tlačítko **moduly**.  
  
     Ve výchozím nastavení **moduly** okno seřadí podle pořadí načítání modulů. Můžete však řadit podle libovolného sloupce.  
  
### <a name="to-sort-by-any-column"></a>Seřadit podle kteréhokoli sloupce  
  
-   Klikněte na tlačítko v horní části sloupce.  
  
     Můžete načíst symboly nebo zadat cestu k symbolům z **moduly** okna pomocí místní nabídky.  
  
## <a name="loading-symbols"></a>Načítání symbolů  
 V **moduly** okně uvidíte, které moduly mají načíst symboly ladění. Tyto informace se zobrazí v **Status symbolu** sloupce. Pokud je stav zobrazeno **vynecháno loadingCannot najít nebo otevřít soubor PDB**, nebo **nastavení zahrnutí a vyloučení zakázalo načtení**, může směrovat ladicího programu ke stažení symbolů ze veřejných symbolů Microsoft servery nebo se načíst symboly z adresáře symbolu v počítači. Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols-manually"></a>Ruční načtení symbolů  
  
1.  V **moduly** okna, klikněte pravým tlačítkem na modul, pro který nejsou načteny symboly.  
  
2.  Přejděte na **načíst symboly z** a potom klikněte na tlačítko **Microsoft Symbol Servers** nebo **cesty k symbolu**.  
  
#### <a name="to-change-symbol-load-settings"></a>Chcete-li změnit nastavení načítání symbolů  
  
1.  V **moduly** okna, klikněte pravým tlačítkem na jakýkoli modul.  
  
2.  Klikněte na tlačítko **Symbol nastavení**.  
  
     Nyní můžete změnit nastavení načítání symbolů, jak je popsáno v [zadejte umístění symbolu a chování načítání](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior). Změny neprojeví až po restartování relace ladění.  
  
#### <a name="to-change-symbol-load-behavior-for-a-specific-module"></a>Ke změně chování načítání symbolů pro konkrétní modul  
  
1.  V **moduly** okna, klikněte pravým tlačítkem na modul.  
  
2.  Přejděte na **nastavení automatické načítání symbolů** a potom klikněte na tlačítko **vždy zatížení ručně** nebo **výchozí**. Změny neprojeví až po restartování relace ladění.  
  
## <a name="see-also"></a>Viz také  
 [Pozastavení provádění](/previous-versions/visualstudio/visual-studio-2010/7z9se2d8(v=vs.100))   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)