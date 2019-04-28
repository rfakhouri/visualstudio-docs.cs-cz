---
title: 'Chyba: Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači běží jako jiný uživatel | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
ms.assetid: e5b18734-2daf-4c58-b5de-24ae1295703e
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7cba3de8aa07a021d61e1ebb2a2c97f568eaf9ee
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63388425"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Chyba: Sledování vzdáleného ladění sady Microsoft Visual Studio je na vzdáleném počítači spuštěné pod jiným uživatelským účtem.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při pokusu o provádět vzdálené ladění, může zobrazit následující chybová zpráva:  
  
 Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači běží jako jiný uživatel.  
  
## <a name="cause"></a>příčina  
 Tato zpráva se zobrazí při ladění v módu bez ověřování a uživatel, který spuštění msvsmon není uživatel, který se systémem Visual Studio.  
  
## <a name="solution"></a>Řešení  
 Nejbezpečnější a nejlepší řešení je pro spuštění sledování vzdáleného ladění (msvsmon.exe) pod stejným uživatelským účtem jako Visual Studio. Pokud nemůžete udělat, můžete pod jiným účtem se spustit sledování vzdáleného ladění **dovolit ladění jakémukoliv uživateli** možnosti vybrané v sledování vzdáleného ladění **možnosti** dialogové okno.  
  
> [!CAUTION]
> Udělení oprávnění pro připojení jiných uživatelů umožňuje možnost nechtěným připojením k nesprávné relace vzdáleného ladění. Ladění v **bez ověřování** režimu se nikdy zabezpečené a by měl třeba používat opatrně.  
  
 Další informace najdete v tématu [spuštění sledování vzdáleného ladění](http://msdn.microsoft.com/library/55b60ce7-834b-4e83-a10e-fe4248260a4c).  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)
