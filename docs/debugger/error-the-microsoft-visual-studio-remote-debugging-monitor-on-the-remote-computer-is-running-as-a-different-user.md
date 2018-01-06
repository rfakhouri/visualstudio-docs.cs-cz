---
title: "Chyba: Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači běží jako jiný uživatel. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f6575dc0d0a71481efff1da7808c7fbc62f94e56
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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