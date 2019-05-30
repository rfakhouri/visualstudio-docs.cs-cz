---
title: Upozornění portu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- ports, notification
ms.assetid: f9fce48e-7d4e-4627-a0fb-77b75428146a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e7ccb4ab9fc36e08f4094baaf1e6b6eee30b2f8
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351507"
---
# <a name="notify-the-port"></a>Upozornění portu
Po spuštění programu, port, který musí být upozorněn, následujícím způsobem:

1. Když port obdrží nový uzel programu, odešle událost vytvoření programu zpět do relace ladění. Událost provede s ní rozhraní, které představuje program.

2. Relace ladění dotazů pro identifikátor ladicího stroje (DE), který může připojit k programu.

3. Kontroluje, jestli DE je na seznamu povolených DEs pro daný program relace ladění. Ladicí relaci získá tento seznam z nastavení aktivní program řešení, původně předána do ní balíček ladění.

    DE musí být na seznamu povolených, jinak je DE nebude připojen k programu.

   Prostřednictvím kódu programu, když je port nejprve obdrží nový uzel program, vytvoří [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní k reprezentaci program.

> [!NOTE]
> Tento model nelze zaměňovat s `IDebugProgram2` rozhraní vytvořit později pomocí ladicího stroje (DE).

 Port, který odešle [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událost vytvoření programu zpět do Správce ladění relace (SDM) prostřednictvím COM `IConnectionPoint` rozhraní.

> [!NOTE]
> Tento model nelze zaměňovat s `IDebugProgramCreateEvent2` rozhraní, které odesílají DE později.

 Spolu s událostí rozhraní samotného, port, který odešle [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md), [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md), a [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, které představují port, zpracovávat, a programování v uvedeném pořadí. Volání SDM [IDebugProgram2::GetEngineInfo](../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md) získat GUID DE, který lze ladit program. Identifikátor GUID byl původně získaných [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní.

 SDM zkontroluje, jestli je DE je na seznamu povolených DEs. Tento seznam SDM získá z nastavení aktivní program řešení, původně předána do ní balíček ladění. DE musí být na seznamu povolených, jinak jej nebude připojen k programu.

 Jakmile identity DE je známo, SDM je připraven pro připojení k programu.

## <a name="see-also"></a>Viz také:
- [Spuštění programu](../../extensibility/debugger/launching-a-program.md)
- [Připojení po spuštění](../../extensibility/debugger/attaching-after-a-launch.md)
- [Ladění úloh](../../extensibility/debugger/debugging-tasks.md)