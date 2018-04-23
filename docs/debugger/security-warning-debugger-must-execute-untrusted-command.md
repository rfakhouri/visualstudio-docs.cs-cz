---
title: 'Upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 77554795772a5a9e2ce5d9bbe9f620923bc20184
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="security-warning-debugger-must-execute-untrusted-command"></a>Upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz.
Toto dialogové okno upozornění se zobrazí, když používáte zdrojového serveru. Znamená to, ladicího programu je potřeba provést k získání zdrojového kódu příkaz není v seznamu důvěryhodných příkazy pro zdrojový Server, které jsou obsažené v souboru srcsvr.ini. Pokud je to platný příkaz, můžete ho přidat do souboru srcsvr.ini. Jinak by neměl spustit ho. Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## <a name="message-text"></a>Text zprávy  
 **Ladicí program musí spustit následující nedůvěryhodný příkaz získat zdrojového kódu ze zdrojového serveru.**  
  
 **Pokud ladění symbolů souboru (\*PDB) není ze známé a důvěryhodné zdroje, tento příkaz může být neplatná nebo nebezpečných ke spuštění.**  
  
 **Opravdu chcete spustit tento příkaz?**  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 Textové pole  
 Příkaz ze souboru PDB ke spuštění.  
  
 Spustit  
 Povolte příkaz ke spuštění.  
  
 Nespouštět  
 Zastavte provádění příkazu a stahování souborů ze zdrojového serveru.  
  
## <a name="see-also"></a>Viz také  
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Zdrojový Server](http://msdn.microsoft.com/library/windows/desktop/ms680641\(v=vs.85\).aspx)