---
title: 'Chyba: Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači nemá oprávnění k připojení k tomuto počítači. | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.error.access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, Windows version error
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4bb71667da94027d3170a372a9a570e5e1eea4ba
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49854166"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>Chyba: Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači nemá oprávnění pro připojení k tomuto počítači.
K této chybě dochází, když uživatel, který se pokouší spustit Visual Studio Remote Debugging Monitor (msvsmon) nemá účet na místním počítači.  
  
### <a name="to-fix-this-problem"></a>Chcete-li vyřešit tento problém  
  
- Přidat uživatelský účet k počítači hostitele ladicího programu sady Visual Studio, pomocí stejné jméno a heslo uživatelského účtu na vzdáleném počítači spuštěny msvsmon.  
  
   \- nebo –  
  
- Spuštění msvsmon jako uživatel, který má oprávnění k volání do místního počítače. To znamená, že uživatel musí být uživatelem domény a správce v počítači msvsmon. Můžete zadat uživatelský účet pro spuštění msvsmon v jednom ze dvou způsobů:  
  
  - Klikněte pravým tlačítkem na ikonu msvsmon a zvolte **spustit jako** v místní nabídce  
  
    \- nebo –  
  
  - Na příkazovém řádku spusťte `runas.exe`.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)