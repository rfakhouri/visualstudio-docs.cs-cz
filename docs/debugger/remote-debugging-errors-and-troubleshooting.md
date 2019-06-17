---
title: Vzdálené ladění chyby a řešení potíží | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, errors
- debugging errors
- remote debugging, troubleshooting
- troubleshooting remote debugging
- errors [debugger], remote debugging
- remote debugging, errors
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 078551111223f11b38f3192075caa9ddfabaf18c
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043344"
---
# <a name="remote-debugging-errors-and-troubleshooting"></a>Chyby a řešení potíží se vzdáleným laděním

Můžete narazit na následující chyby při pokusu o vzdálené ladění.

- [Chyba: Automatické krokování s vnořením do serveru se nezdařilo.](../debugger/error-unable-to-automatically-step-into-the-server.md)

- [Chyba: Na vzdáleném počítači pravděpodobně neběží sledování vzdáleného ladění sady Microsoft Visual Studio (MSVSMON.EXE).](/visualstudio/debugger/error-remote-debugging-monitor-msvsmon-exe-does-not-appear-to-be-running)

- [Nepodařilo se připojit ke sledování vzdáleného ladění sady Microsoft Visual Studio.](../debugger/unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor.md)

- [Chyba: Vzdálený počítač se nezobrazuje v dialogovém okně Vzdálená připojení.](../debugger/error-remote-machine-does-not-appear-in-a-remote-connections-dialog.md)

## <a name="run-the-remote-debugger-as-an-administrator"></a>Spustit vzdálený ladicí program jako správce

Můžete narazit na problémy při spuštění vzdáleného ladícího programu jako správce. Například může zobrazit následující chybová zpráva: "Visual Studio Remote Debugger (MSVSMON. Soubor EXE) nemá dostatečná oprávnění pro ladění tohoto procesu." Pokud používáte vzdálený ladicí program jako aplikace (nikoli služba), může se zobrazit [jiného uživatelského účtu](error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user.md) chyby.

### <a name="when-running-the-remote-debugger-as-a-service"></a>Při spuštění vzdáleného ladícího programu jako služba

Při spuštění vzdáleného ladícího programu jako služba s, doporučujeme spuštění jako správce z několika důvodů:

- Služba vzdáleného ladicího programu pouze umožňuje připojení z správci, aby vás nečekala **žádné** nové bezpečnostní rizika zavedené spuštěním jako správce.

- To může zabránit chybám jako výsledek, pokud má uživatel Visual Studio další práva k ladění procesu než samotný vzdálený ladicí program.

- Pro zjednodušení instalace a konfigurace vzdáleného ladicího programu.

I když je možné ladit bez spuštění vzdáleného ladícího programu jako správce, existuje několik požadavků správně provést tuto práci a často vyžadují pokročilejší kroky konfigurace služby.

- Používáte ve vzdáleném počítači účet musí mít **přihlásit jako službu** oprávnění. Přečtěte si postup v části "Přidání přihlášení jako služba" najdete v [nemůže připojit zpět](error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md) chyba článku.

- Účet musí mít oprávnění k ladění cílového procesu. Chcete-li získat tato práva, musíte spustit vzdálený ladicí program pod stejným účtem jako proces, který chcete ladit. (Jednodušší alternativou je spuštění služby jako správce.) 

- Účet musí být schopný se připojit zpět k (to znamená, ověřování pomocí) sady Visual Studio počítače v síti. V doméně je jednodušší připojit zpět v případě, že vzdálený ladicí program je spuštěn v rámci předdefinované účty místní systém nebo síťovou službu nebo účet domény. Předdefinované účty musí mít zvýšená oprávnění zabezpečení, které může představovat bezpečnostní riziko.

### <a name="when-running-the-remote-debugger-as-an-application-normal-mode"></a>Při spuštění vzdáleného ladícího programu jako aplikace (běžný režim)

Pokud se pokoušíte připojit k procesu vlastní bez zvýšených (jako je například běžné aplikace), nebude vadit, když používáte vzdálený ladicí program jako správce.

Chcete spustit vzdálený ladicí program jako správce v několika situacích:

- Chcete se připojit k procesům spuštěnému jako jiný uživatel (třeba při ladění služby IIS), nebo

- Pokoušíte se spustit jiným procesem a proces, který chcete spustit správce.

Provedete **není** chcete spustit jako správce, pokud chcete spustit procesy a měli byste procesu, kterou chcete spustit **není** mít oprávnění správce.

## <a name="see-also"></a>Viz také
- [Vzdálené ladění](../debugger/remote-debugging.md)