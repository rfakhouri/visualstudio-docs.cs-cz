---
title: Upozornění portu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- ports, notification
ms.assetid: f9fce48e-7d4e-4627-a0fb-77b75428146a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b022cca2b69c8cb80b24fa34e3b020923cff4022
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689197"
---
# <a name="notify-the-port"></a>Upozornění portu
Po spuštění programu, port, který musí být upozorněn, následujícím způsobem:

1. Když port obdrží nový uzel programu, odešle událost vytvoření programu zpět do relace ladění. Událost provede s ní rozhraní, které představuje program.

2. Relace ladění dotazů pro identifikátor ladicího stroje (DE), který může připojit k programu.

3. Kontroluje, jestli DE je na seznamu povolených DEs pro daný program relace ladění. Ladicí relaci získá tento seznam z nastavení aktivní program řešení, původně předána do ní balíček ladění.

    DE musí být na seznamu povolených, jinak je DE nebude připojen k programu.

   Prostřednictvím kódu programu, když je port nejprve obdrží nový uzel program, vytvoří [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní k reprezentaci program.

> [!NOTE]
>  Tento model nelze zaměňovat s `IDebugProgram2` rozhraní vytvořit později pomocí ladicího stroje (DE).

 Port, který odešle [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událost vytvoření programu zpět do Správce ladění relace (SDM) prostřednictvím COM `IConnectionPoint` rozhraní.

> [!NOTE]
>  Tento model nelze zaměňovat s `IDebugProgramCreateEvent2` rozhraní, které odesílají DE později.

 Spolu s událostí rozhraní samotného, port, který odešle [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md), [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md), a [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, které představují port, zpracovávat, a programování v uvedeném pořadí. Volání SDM [IDebugProgram2::GetEngineInfo](../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md) získat GUID DE, který lze ladit program. Identifikátor GUID byl původně získaných [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní.

 SDM zkontroluje, jestli je DE je na seznamu povolených DEs. Tento seznam SDM získá z nastavení aktivní program řešení, původně předána do ní balíček ladění. DE musí být na seznamu povolených, jinak jej nebude připojen k programu.

 Jakmile identity DE je známo, SDM je připraven pro připojení k programu.

## <a name="see-also"></a>Viz také:
- [Spuštění programu](../../extensibility/debugger/launching-a-program.md)
- [Připojení po spuštění](../../extensibility/debugger/attaching-after-a-launch.md)
- [Ladění úloh](../../extensibility/debugger/debugging-tasks.md)