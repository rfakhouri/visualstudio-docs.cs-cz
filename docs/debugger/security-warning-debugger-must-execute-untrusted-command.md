---
title: 'Upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz. | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.securityalert
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: e5c004b3-b364-4098-ac98-770076ca9981
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce5fd0820bcbd1f047bfe556f8e70b3382c9fe64
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54982621"
---
# <a name="security-warning-debugger-must-execute-untrusted-command"></a>Upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz.
Toto dialogové okno upozornění se zobrazí při použití zdrojového serveru. Znamená to, že příkaz, který ladicí program potřebuje provést, aby získal zdrojový kód není v seznamu důvěryhodných příkazů pro zdrojový Server obsaženém v souboru srcsvr.ini. Pokud se jedná o platný příkaz, můžete ho přidat do souboru srcsvr.ini. Jinak není spouštění vhodné. Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## <a name="message-text"></a>Text zprávy  
 **Ladicí program musí spustit nedůvěryhodný příkaz pro získání zdrojového kódu ze zdrojového serveru.**  
  
 **Pokud soubor symbolů ladění (\*PDB) je tohoto příkazu není od známých a důvěryhodných zdrojů, může být nevhodné nebo nebezpečné ke spuštění.**  
  
 **Chcete spustit tento příkaz?**  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 Textové pole  
 Ke spuštění příkazu ze souboru .pdb.  
  
 Spustit  
 Povolte příkaz ke spuštění.  
  
 Nespouštět  
 Zastavení spuštění příkazu a stahování souborů ze zdrojového serveru.  
  
## <a name="see-also"></a>Viz také  
 [Zadání symbolu (.pdb) a zdrojové soubory](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Zdrojový Server](/windows/desktop/Debug/source-server-and-source-indexing)