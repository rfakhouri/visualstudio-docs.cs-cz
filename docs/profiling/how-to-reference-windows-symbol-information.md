---
title: "Postupy: referenční informace o symbolech Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, symbol servers
- servers, symbol servers
- profiling tools, symbol servers
- symbol servers
ms.assetid: b7c67318-6be2-4b1e-a161-077b1f4a7c30
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09e17cc1e28ad520f76d60c3411de4803a2b4b96
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-reference-windows-symbol-information"></a>Postupy: Referenční informace o symbolech Windows
Visual Studio Tools profilace soubory symbolu (.pdb) použít k vyřešení symbolický názvy, například názvy funkcí v binárních souborech programu. Můžete provést tyto kroky automaticky stáhnout a aktualizovat soubory PDB správné pro verzi systému Windows v místním počítači.  
  
> [!NOTE]
>  Toto nastavení nemá vliv na existující sestavy. Pouze sestavy vytvořené po zadání serveru symbol bude mít informací o symbolu.  
  
 Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
### <a name="to-use-the-microsoft-symbol-server"></a>Použití serveru Microsoft – symbol  
  
1.  Vytvořte složku tak, aby obsahovala symbol informací o souboru, jako je například C:\SymbolCache.  
  
2.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
     **Možnosti** zobrazí se dialogové okno.  
  
3.  Rozbalte **ladění** stromu a pak klikněte na **symboly**.  
  
4.  V **symbolů umístění souborů (.pdb)**, vyberte **servery Microsoft symbolů**  
  
5.  V **mezipaměti symboly ze serveru symbol do tohoto adresáře**, zadejte cestu ke složce, který byl vytvořen v kroku 1, například:  
  
     **C:\SymbolCache**  
  
     Můžete také kliknutím tlačítko se třemi tečkami (**...** ) a poté vyberte adresář z **vyhledat složku** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Postupy: serializace informací o symbolu](../profiling/how-to-serialize-symbol-information.md)