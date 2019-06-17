---
title: 'Chyba: Sledování vzdáleného ladění sady Microsoft Visual Studio na vzdáleném počítači nemá oprávnění pro připojení k tomuto počítači.'
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: troubleshooting
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9cafbd6a6c9c6844028b1b18d0ebfe7afd8ddf57
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043442"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>Chyba: Sledování vzdáleného ladění sady Microsoft Visual Studio na vzdáleném počítači nemá oprávnění pro připojení k tomuto počítači.

K této chybě dochází, když uživatel, který se pokouší spustit Visual Studio Remote Debugging Monitor (msvsmon) nemá účet na místním počítači. K této chybě může dojít při vzdáleném ladění pomocí starší verze modulu pro ladění.

## <a name="to-fix-this-problem"></a>Chcete-li vyřešit tento problém

- Přidat uživatelský účet k počítači hostitele ladicího programu sady Visual Studio, pomocí stejné jméno a heslo uživatelského účtu na vzdáleném počítači spuštěny msvsmon.

   \- nebo –

- Spuštění msvsmon jako uživatel, který má oprávnění k volání do místního počítače. To znamená, že uživatel musí být uživatelem domény a správce v počítači msvsmon. Můžete zadat uživatelský účet pro spuštění msvsmon v jednom ze dvou způsobů:

  - Klikněte pravým tlačítkem na ikonu msvsmon a zvolte **spustit jako** v místní nabídce

    \- nebo –

  - Na příkazovém řádku spusťte `runas.exe`.

## <a name="see-also"></a>Viz také:

- [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)