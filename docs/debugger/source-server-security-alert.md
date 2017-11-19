---
title: "Zdroj výstraha zabezpečení serveru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.sourceserver.enablewarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7eb50bec1967b9c1f7a969eb802888864f5e72eb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="source-server-security-alert"></a>Výstraha zabezpečení zdrojového serveru
Při použití zdrojového serveru, použijte pouze symbol soubory, které jsou z umístění známé a důvěryhodné.  
  
 Toto upozornění se zobrazí, když povolíte podporu zdrojového serveru. Příkazy zdrojového serveru jsou součástí soubory ladění symbol (***PDB** soubory). Ujistěte se, že znáte, odkud pocházejí vaše soubory PDB.  
  
> [!IMPORTANT]
>  Následující potenciální bezpečnostní hrozby musí vzít v úvahu při použití zdrojového serveru: libovolný příkazy může být vložen do souboru PDB aplikace, proto se ujistěte, můžete zadat jenom ty, které chcete provést v souboru srcsrv.ini. Pokus o provedení příkazu mimo soubor srcsvr.ini způsobí zobrazení dialogového okna s potvrzením. Další informace najdete v tématu [upozornění zabezpečení: ladicí program musí spustit nedůvěryhodný příkaz](../debugger/security-warning-debugger-must-execute-untrusted-command.md). Na parametry příkazu není prováděno žádné ověření, tak buďte opatrní pomocí důvěryhodného příkazů. Například pokud důvěřujete souboru cmd.exe, uživateli se zlými úmysly může zadat parametry, které by z příkazu mohly udělat hrozbu.  
  
## <a name="see-also"></a>Viz také  
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Zdrojový Server](http://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)