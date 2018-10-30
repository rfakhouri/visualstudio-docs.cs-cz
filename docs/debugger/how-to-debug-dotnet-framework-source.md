---
title: 'Postupy: ladění zdroje rozhraní .NET Framework | Dokumentace Microsoftu'
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
ms.openlocfilehash: c06a2328987201198bc2d5d15a4788d2a821d7b6
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2018
ms.locfileid: "50219117"
---
# <a name="how-to-debug-net-framework-source"></a>Postupy: Ladění zdroje rozhraní .NET Framework
Ladění zdroje rozhraní .NET Framework, musíte mít přístup k symbolům ladění pro kód. Je také potřeba povolit krokování s vnořením do zdroje rozhraní.NET Framework.  
  
 Můžete povolit rozhraní .NET Framework kroky a stahování v symbolu **možnosti** dialogové okno. Když povolíte stahování symbolů, můžete stáhnout symboly hned nebo Povolit jenom možnost pro pozdější stažení. Pokud okamžitě nestáhnete symboly, symboly budou staženy při příštím spuštění ladění vaší aplikace. Můžete také provést ruční stažení z **moduly** okno nebo **zásobník volání** okna.  
  
### <a name="to-enable-net-framework-source-debugging"></a>Chcete-li povolit ladění zdrojového kód rozhraní .NET Framework  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  V **možnosti** dialogové okno, klikněte na tlačítko **ladění** kategorie.  
  
3.  V **Obecné** pole, nastavte **zdroje povolit rozhraní .NET Framework krokování.**  
  
    1.  Pokud jste měli povoleným kódem Just My, dialogové okno upozornění zjistíte, že funkce pouze můj kód je nyní zakázána. Klikněte na tlačítko **OK**.  
  
    2.  Pokud nastaveno umístění mezipaměti symbolů, jiné dialogové okno upozornění informuje, že výchozí umístění mezipaměti symbolů je nyní nastaveno. Klikněte na tlačítko **OK**.  
  
4.  V části **ladění** kategorii, klikněte na tlačítko **symboly**.  
  
5.  Pokud chcete změnit umístění mezipaměti symbolů, upravte umístění v **mezipaměti symbolů v tomto adresáři** nebo klikněte na tlačítko **Procházet** k výběru umístění.  
  
6.  Pokud chcete stáhnout symboly hned, klikněte na tlačítko **načíst symboly pomocí výše uvedených umístění**.  
  
     Toto tlačítko není k dispozici v režimu návrhu, ale je k dispozici při ladění.  
  
     Pokud nevyberete nyní nestahovat symboly, symboly budou staženy automaticky při příštím spuštění ladění programu.  
  
7.  Klikněte na tlačítko **OK** zavřete **možnosti** dialogové okno.  
  
### <a name="to-load-framework-symbols-using-the-modules-window"></a>Načtení symbolů rozhraní pomocí okna modulů  
  
1.  V **moduly** okno (při ladění, zvolte **ladění** > **Windows** > **moduly**), Klikněte pravým tlačítkem na modul, pro který nejsou načteny symboly. Poznáte, zda jsou načteny symboly nebo není zobrazením **symboly stavu** sloupce.  
  
2.  Přejděte na **nastavení symbolu** a klikněte na tlačítko **Microsoft Symbol Servers** ke stažení symbolů ze serveru veřejných symbolů Microsoft. Nebo můžete klikněte pravým tlačítkem na modul a vyberte **načíst symboly** k načtení z adresáře, kam jste dříve uložili symboly.  
  
### <a name="to-load-framework-symbols-using-the-call-stack-window"></a>Načtení symbolů rozhraní pomocí okna zásobník volání  
  
1.  V **zásobník volání** okna, klikněte pravým tlačítkem na rámec, pro který nejsou načteny symboly. Snímek bude znepřístupněn.  
  
2.  Přejděte na **nastavení symbolu** a klikněte na tlačítko **Microsoft Symbol Servers**, nebo klikněte pravým tlačítkem na modul a vyberte **cesty k symbolu**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)