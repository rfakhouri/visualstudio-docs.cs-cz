---
title: Výstraha zabezpečení serveru zdroje | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3f8b122deab5dbdc30b129bce221a804f8c53aa3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65699328"
---
# <a name="source-server-security-alert"></a>Výstraha zabezpečení zdrojového serveru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při použití zdrojového serveru, používejte pouze soubory symbolů, které jsou ze známých a důvěryhodných umístění.  
  
 Toto upozornění se zobrazí, když povolíte podporu zdrojového serveru. Příkazy ze zdrojového serveru jsou vloženy do souborů symbolů ladění (soubory PDB). Ujistěte se, že budete vědět, odkud pochází vaše soubory PDB.  
  
> [!IMPORTANT]
> Následující potenciální ohrožení zabezpečení se musí vzít v úvahu při použití zdrojového serveru: Libovolné příkazy lze vložit do souboru PDB aplikace, proto se ujistěte, že vložíte pouze ty, které chcete spustit v souboru srcsrv.ini. Pokus o provedení příkazu mimo soubor srcsvr.ini způsobí zobrazení dialogového okna s potvrzením. Další informace najdete v tématu [upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz](../debugger/security-warning-debugger-must-execute-untrusted-command.md). Žádné ověření se provádí na parametry příkazu, proto buďte s důvěryhodnými příkazy opatrní. Například pokud důvěřujete souboru cmd.exe, uživateli se zlými úmysly může zadat parametry, které by z příkazu mohly udělat hrozbu.  
  
## <a name="see-also"></a>Viz také  
 [Zadání symbolu (.pdb) a zdrojové soubory](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Zdrojový Server](https://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)
