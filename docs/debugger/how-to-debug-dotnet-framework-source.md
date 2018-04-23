---
title: 'Postupy: ladění zdroje rozhraní .NET Framework | Microsoft Docs'
ms.custom: ''
ms.date: 02/23/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugging, .NET Framework source
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 8377ed73479441272b2f1910767fa7e2a4ff0196
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-debug-net-framework-source"></a>Postupy: Ladění zdroje rozhraní .NET Framework
K ladění .NET Framework – zdroj, musí mít přístup k ladění symboly pro kód. Musíte také povolit zanoříte se do zdroje rozhraní .NET Framework.  
  
 Můžete povolit rozhraní .NET Framework krokování a symbol stahování v **možnosti** dialogové okno. Když povolíte symbol stahování, můžete stáhnout symboly okamžitě nebo Povolit jenom možnost pro stahování později. Pokud jste symboly nestahovat okamžitě, symboly stáhnout při příštím spuštění ladění aplikace. Můžete také provést ruční stažení z **moduly** okno nebo **zásobníkem volání** okno.  
  
### <a name="to-enable-net-framework-source-debugging"></a>Pokud chcete povolit ladění zdroje rozhraní .NET Framework  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnost**s.  
  
2.  V **možnosti** dialogové okno, klikněte **ladění** kategorie.  
  
3.  V **Obecné** nastavte **povolit .NET Framework – zdroj krokování s.**  
  
    1.  Pokud jste měli pouze můj kód povoleno, dialogové okno upozornění informuje, že pouze můj kód je nyní zakázán. Click **OK**.  
  
    2.  Pokud umístění mezipaměti symbol nastavit neměl, jiné dialogové okno upozornění okno se zprávou, že výchozí umístění mezipaměti symbol je teď nastavená. Click **OK**.  
  
4.  V části **ladění** kategorii, klikněte na tlačítko **symboly**.  
  
5.  Pokud chcete změnit umístění mezipaměti symboly, upravit umístění v **mezipaměti symboly v tomto adresáři** nebo klikněte na tlačítko **Procházet** vyberte jiné umístění.  
  
6.  Pokud chcete stáhnout symboly okamžitě, klikněte na tlačítko **zatížení symboly pomocí výše umístění**.  
  
     Toto tlačítko není k dispozici v režimu návrhu, ale je k dispozici při ladění.  
  
     Pokud nevyberete stáhnout symboly, symboly stáhnou automaticky při příštím spuštění ladění vašeho programu.  
  
7.  Klikněte na tlačítko **OK** zavřete **možnosti** dialogové okno.  
  
### <a name="to-load-framework-symbols-using-the-modules-window"></a>Chcete-li načíst Framework symboly pomocí okna moduly  
  
1.  V **moduly** okno (při ladění, zvolte **ladění** > **Windows** > **moduly**), Klikněte pravým tlačítkem na modul, u kterého symboly nenačtou. Můžete zadat, pokud se načtou symboly nebo není prohlížením **symboly stav** sloupce.  
  
2.  Přejděte na příkaz **Symbol nastavení** a klikněte na tlačítko **servery symbolů Microsoft** ke stažení ze serveru Microsoft veřejné symboly symboly. Nebo můžete klikněte pravým tlačítkem na modul a vyberte **načíst symboly** načíst z adresáře, kam jste dřív uložili symboly.  
  
### <a name="to-load-framework-symbols-using-the-call-stack-window"></a>Chcete-li načíst Framework symboly pomocí okno zásobník volání  
  
1.  V **zásobníkem volání** okna, klikněte pravým tlačítkem a rámečku, pro který symboly nenačtou. Limit bude nedostupné rámečku.  
  
2.  Přejděte na příkaz **Symbol nastavení** a klikněte na tlačítko **servery symbolů Microsoft**, nebo klikněte pravým tlačítkem na modul a vyberte **Symbol cesta**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)