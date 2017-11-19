---
title: "Chyba: Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači běží jako jiný uživatel. | Microsoft Docs"
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
- JScript
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
ms.assetid: e5b18734-2daf-4c58-b5de-24ae1295703e
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5f3f2c9e0b3f88734d21ae06f1af48409c58766a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Chyba: Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači běží jako jiný uživatel.
Při pokusu provést vzdálené ladění, zobrazí se následující chybová zpráva:  
  
 Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači běží jako jiný uživatel.  
  
## <a name="cause"></a>příčina  
 Tato zpráva se zobrazí, když ladíte v režimu bez ověřování a uživatele, který spustil msvsmon není uživatel, který běží v sadě Visual Studio.  
  
## <a name="solution"></a>Řešení  
 Co možná nejbezpečnějším a nejlepší řešení je spustit Remote Debugging Monitor (msvsmon.exe) pod stejným účtem uživatele jako Visual Studio. Pokud nejde udělat, můžete spustit sledování vzdáleného ladění pod jiným účtem se **umožnit všem uživatelům ladění** možnosti vybrané v sledování vzdáleného ladění **možnosti** dialogové okno.  
  
> [!CAUTION]
>  Udělení oprávnění k připojení jiných uživatelů umožňuje možnost náhodně připojení k nesprávné vzdálenou relaci ladění. Ladění v **bez ověřování** režimu se nikdy zabezpečené a musí být použit s opatrní.
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)