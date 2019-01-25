---
title: 'Postupy: Informace o symbolech Windows odkaz | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, symbol servers
- servers, symbol servers
- profiling tools, symbol servers
- symbol servers
ms.assetid: b7c67318-6be2-4b1e-a161-077b1f4a7c30
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8819964eff232cc01cbcfc2081e01eca47f04c15
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54801697"
---
# <a name="how-to-reference-windows-symbol-information"></a>Postupy: Referenční informace o symbolech Windows
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio Tools pro profilaci symbolické názvy, například názvy funkcí v binárních souborech programu použít soubory symbolů (PDB). Provedením tohoto postupu automaticky stáhnout a aktualizovat soubory s příponou .pdb správná verze Windows na místním počítači.  
  
> [!NOTE]
>  Toto nastavení nemá vliv na existující sestavy. Pouze sestavy vytvořené po zadání serveru symbolů, bude mít informace o symbolech.  
  
 Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
### <a name="to-use-the-microsoft-symbol-server"></a>Chcete-li použít Microsoft symbol server  
  
1.  Vytvoření složky obsahující informace o souboru symbolů, jako je například C:\SymbolCache.  
  
2.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
     **Možnosti** zobrazí se dialogové okno.  
  
3.  Rozbalte **ladění** stromu a pak klikněte na tlačítko **symboly**.  
  
4.  V **Symbol umístění souborů (.pdb)** vyberte **servery symbolů společnosti Microsoft**  
  
5.  V **mezipaměti symbolů ze serveru symbolů do tohoto adresáře**, zadejte cestu ke složce, která byla vytvořena v kroku 1, například:  
  
     **C:\SymbolCache**  
  
     Můžete také kliknout na tlačítko se třemi tečkami (**...** ) a potom vyberte adresář z **přejít ke složce** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Postupy: Serializace informací o symbolu](../profiling/how-to-serialize-symbol-information.md)
