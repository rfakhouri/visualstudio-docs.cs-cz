---
title: 'Postupy: Použití okna moduly | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.modules
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Modules window
- Modules window
- executable files, displaying while debugging
- debugging [Visual Studio], displaying modules
- DLLs, displaying while debugging
- modules, displaying
ms.assetid: d840fdca-b035-4452-b652-72580c831896
caps.latest.revision: 41
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2f332ef1a52ae49e51025614745fc1b5c4a44e07
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60078281"
---
# <a name="how-to-use-the-modules-window"></a>Postupy: Použití okna moduly
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

POZNÁMKA:]
>  Tato funkce není k dispozici pro SQL nebo ladění skriptů.  
  
 **Moduly** okně zobrazí knihovny DLL a EXE, které jsou používané vaším programem a zobrazuje relevantní informace pro každý.  
  
### <a name="to-display-the-modules-window-in-break-mode-or-in-run-mode"></a>Chcete-li zobrazit okno moduly v režimu přerušení nebo v režimu spuštění  
  
- Na **ladění** nabídce zvolte **Windows**a potom klikněte na tlačítko **moduly**.  
  
     Ve výchozím nastavení **moduly** okno seřadí podle pořadí načítání modulů. Můžete však řadit podle libovolného sloupce.  
  
### <a name="to-sort-by-any-column"></a>Seřadit podle kteréhokoli sloupce  
  
- Klikněte na tlačítko v horní části sloupce.  
  
     Můžete načíst symboly nebo zadat cestu k symbolům z **moduly** okna pomocí místní nabídky.  
  
## <a name="loading-symbols"></a>Načítání symbolů  
 V **moduly** okně uvidíte, které moduly mají načíst symboly ladění. Tyto informace se zobrazí v **Status symbolu** sloupce. Pokud je stav zobrazeno **vynecháno loadingCannot najít nebo otevřít soubor PDB**, nebo **nastavení zahrnutí a vyloučení zakázalo načtení**, může směrovat ladicího programu ke stažení symbolů ze veřejných symbolů Microsoft servery nebo se načíst symboly z adresáře symbolu v počítači. Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols-manually"></a>Ruční načtení symbolů  
  
1. V **moduly** okna, klikněte pravým tlačítkem na modul, pro který nejsou načteny symboly.  
  
2. Přejděte na **načíst symboly z** a potom klikněte na tlačítko **Microsoft Symbol Servers** nebo **cesty k symbolu**.  
  
#### <a name="to-change-symbol-load-settings"></a>Chcete-li změnit nastavení načítání symbolů  
  
1. V **moduly** okna, klikněte pravým tlačítkem na jakýkoli modul.  
  
2. Klikněte na tlačítko **Symbol nastavení**.  
  
     Nyní můžete změnit nastavení načítání symbolů, jak je popsáno v [zadejte umístění symbolu a chování načítání](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior). Změny neprojeví až po restartování relace ladění.  
  
#### <a name="to-change-symbol-load-behavior-for-a-specific-module"></a>Ke změně chování načítání symbolů pro konkrétní modul  
  
1. V **moduly** okna, klikněte pravým tlačítkem na modul.  
  
2. Přejděte na **nastavení automatické načítání symbolů** a potom klikněte na tlačítko **vždy zatížení ručně** nebo **výchozí**. Změny neprojeví až po restartování relace ladění.  
  
## <a name="see-also"></a>Viz také  
 [Pozastavení provádění](http://msdn.microsoft.com/30fc4643-f337-4651-b1ff-f2de2c098d40)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
