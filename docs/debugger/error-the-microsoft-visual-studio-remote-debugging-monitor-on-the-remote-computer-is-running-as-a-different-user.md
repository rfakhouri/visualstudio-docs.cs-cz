---
title: 'Chyba: Sledování vzdáleného ladění sady Microsoft Visual Studio je na vzdáleném počítači spuštěné pod jiným uživatelským účtem.'
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: troubleshooting
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d6d36844883b1acd51d169015a226d584c6c096
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53911296"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Chyba: Sledování vzdáleného ladění sady Microsoft Visual Studio je na vzdáleném počítači spuštěné pod jiným uživatelským účtem.
Při pokusu o provádět vzdálené ladění, může zobrazit následující chybová zpráva:  
  
 Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači běží jako jiný uživatel.  
  
## <a name="cause"></a>příčina  
 Tato zpráva se zobrazí při ladění v módu bez ověřování a uživatel, který spuštění msvsmon není uživatel, který se systémem Visual Studio.  
  
## <a name="solution"></a>Řešení  
 Nejbezpečnější a nejlepší řešení je pro spuštění sledování vzdáleného ladění (msvsmon.exe) pod stejným uživatelským účtem jako Visual Studio. Pokud nemůžete udělat, můžete pod jiným účtem se spustit sledování vzdáleného ladění **dovolit ladění jakémukoliv uživateli** možnosti vybrané v sledování vzdáleného ladění **možnosti** dialogové okno.  
  
> [!CAUTION]
>  Udělení oprávnění pro připojení jiných uživatelů umožňuje možnost nechtěným připojením k nesprávné relace vzdáleného ladění. Ladění v **bez ověřování** režimu se nikdy zabezpečené a by měl třeba používat opatrně.
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)