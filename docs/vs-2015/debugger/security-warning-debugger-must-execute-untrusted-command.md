---
title: 'Upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz. | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.securityalert
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e5c004b3-b364-4098-ac98-770076ca9981
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2a29ba026f9b3c2b8839d474c2d0833eb79f7ffd
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65683299"
---
# <a name="security-warning-debugger-must-execute-untrusted-command"></a>Upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
 [Zdrojový Server](https://msdn.microsoft.com/library/windows/desktop/ms680641\(v=vs.85\).aspx)
