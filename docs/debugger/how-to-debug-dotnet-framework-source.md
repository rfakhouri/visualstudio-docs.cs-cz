---
title: "Postupy: ladění zdroje rozhraní .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
helpviewer_keywords: debugging, .NET Framework source
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9da2cd7b8a99d750692a69be406c9c8f82c461d1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-net-framework-source"></a>Postupy: Ladění zdroje rozhraní .NET Framework
Nejnovější verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] poskytuje nové funkce pro [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ladění. Chcete-li ladit [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] zdroje, musíte mít přístup k ladění symboly pro kód. Je také nutné povolit zanoříte se do [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] zdroje.  
  
 Můžete povolit [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] krokování a symbol stahování v **možnosti** dialogové okno. Když povolíte symbol stahování, můžete stáhnout symboly okamžitě nebo Povolit jenom možnost pro stahování později. Pokud jste symboly nestahovat okamžitě, symboly stáhnout při příštím spuštění ladění aplikace. Můžete také provést ruční stažení z **moduly** okno nebo **zásobníkem volání** okno.  
  
### <a name="to-enable-net-framework-source-debugging"></a>Pokud chcete povolit ladění zdroje rozhraní .NET Framework  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnost**s.  
  
2.  V **možnosti** dialogové okno, klikněte **ladění** kategorie.  
  
3.  V **Obecné** nastavte **povolení rozhraní .NET Framework** zdroje krokování s.  
  
    1.  Pokud jste měli pouze můj kód povoleno, dialogové okno upozornění informuje, že pouze můj kód je nyní zakázán. Click **OK**.  
  
    2.  Pokud umístění mezipaměti symbol nastavit neměl, jiné dialogové okno upozornění okno se zprávou, že výchozí umístění mezipaměti symbol je teď nastavená. Click **OK**.  
  
4.  V části **ladění** kategorii, klikněte na tlačítko **symboly**.  
  
5.  Pokud chcete změnit umístění mezipaměti symboly:  
  
    1.  Otevřete **ladění** uzlu v poli na levé straně.  
  
    2.  V části **ladění** uzel, klikněte na tlačítko **symboly**.  
  
    3.  Upravit umístění v **mezipaměti symboly z servery symbolů pro tento adresář** nebo klikněte na tlačítko **Procházet** vyberte jiné umístění.  
  
6.  Pokud chcete stáhnout symboly okamžitě, klikněte na tlačítko **zatížení symboly pomocí výše umístění**.  
  
     Toto tlačítko není k dispozici v režimu návrhu.  
  
     Pokud nevyberete stáhnout symboly, symboly stáhnou automaticky při příštím spuštění ladění vašeho programu.  
  
7.  Klikněte na tlačítko **OK** zavřete **možnosti** dialogové okno.  
  
### <a name="to-load-framework-symbols-using-the-modules-window"></a>Chcete-li načíst Framework symboly pomocí okna moduly  
  
1.  V **moduly** okna, klikněte pravým tlačítkem a modul, u kterého symboly nenačtou. Můžete zadat, pokud se načtou symboly nebo není prohlížením **symboly stav** sloupce.  
  
2.  Přejděte na příkaz **načíst symboly z** a klikněte na tlačítko **servery symbolů Microsoft** ke stažení ze serveru Microsoft veřejné symboly symboly nebo **Symbol cesta** načíst z adresáře kde jsou uloženy dříve symboly.  
  
### <a name="to-load-framework-symbols-using-the-call-stack-window"></a>Chcete-li načíst Framework symboly pomocí okno zásobník volání  
  
1.  V **zásobníkem volání** okna, klikněte pravým tlačítkem a rámečku, pro který symboly nenačtou. Limit bude nedostupné rámečku.  
  
2.  Přejděte na příkaz **zatížení symboly z** a klikněte na tlačítko **servery symbolů Microsoft** nebo **Symbol cesta**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)