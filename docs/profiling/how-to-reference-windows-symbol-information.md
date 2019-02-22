---
title: 'Postupy: Informace o symbolech Windows odkaz | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- performance tools, symbol servers
- servers, symbol servers
- profiling tools, symbol servers
- symbol servers
ms.assetid: b7c67318-6be2-4b1e-a161-077b1f4a7c30
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 347b35a1ed47236c0d6e6c187224ee50fd79852c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56619885"
---
# <a name="how-to-reference-windows-symbol-information"></a>Postupy: Odkazování na informace o symbolech Windows
Symbol použít profilování nástroje sady Visual Studio (. *soubor PDB*) soubory přeložil symbolické názvy, například názvy funkcí v aplikaci binární soubory. Provedením tohoto postupu automaticky stáhnout a aktualizujte správný. *pdb* soubory pro verzi systému Windows v místním počítači.

> [!NOTE]
>  Toto nastavení nemá vliv na existující sestavy. Pouze sestavy vytvořené po zadání serveru symbolů, bude mít informace o symbolech.

 Další informace najdete v tématu [zadání symbolu (. *soubor PDB*) a zdrojové soubory](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).

### <a name="to-use-the-microsoft-symbol-server"></a>Chcete-li použít Microsoft symbol server

1.  Vytvoření složky obsahující informace o souboru symbolů, jako je například C:\SymbolCache.

2.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.

     **Možnosti** zobrazí se dialogové okno.

3.  Rozbalte **ladění** stromu a pak klikněte na tlačítko **symboly**.

4.  V **Symbol umístění souborů (.pdb)** vyberte **servery symbolů společnosti Microsoft**

5.  V **mezipaměti symbolů ze serveru symbolů do tohoto adresáře**, zadejte cestu ke složce, která byla vytvořena v kroku 1, například:

     **C:\SymbolCache**

     Můžete také kliknout na tlačítko se třemi tečkami (**...** ) a potom vyberte adresář z **přejít ke složce** dialogové okno.

## <a name="see-also"></a>Viz také:
- [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
- [Postupy: Serializace informací o symbolu](../profiling/how-to-serialize-symbol-information.md)