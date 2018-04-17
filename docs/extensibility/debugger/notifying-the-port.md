---
title: Upozornění Port | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports, notification
ms.assetid: f9fce48e-7d4e-4627-a0fb-77b75428146a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1420ca8768ddf1eaedc0d515810bc88b3491c4db
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="notifying-the-port"></a>Upozornění portu
Po spuštění programu, port musí být upozorněni, následujícím způsobem:  
  
1.  Když na port obdrží nový uzel program, odešle událost vytvoření programu zpět na relaci ladění. Událost s ním představuje rozhraní, které představuje program.  
  
2.  Relaci ladění dotazy pro identifikátor modul ladění (DE), který můžete připojit k programu.  
  
3.  Kontroluje, zda DE je na seznamu povolených DEs pro daný program relaci ladění. Relaci ladění získá tento seznam z nastavení active programu na řešení, původně předaný balíček ladění.  
  
     DE musí být v seznamu povolených, jinak je DE nebude připojen k programu.  
  
 Prostřednictvím kódu programu, když na port nejprve obdrží nový uzel program, vytvoří se [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní představují program.  
  
> [!NOTE]
>  Tento model nelze zaměňovat s `IDebugProgram2` rozhraní vytvořit později modul ladění (DE).  
  
 Port odešle [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událost vytvoření programu zpět do správce ladicí relace (SDM) prostřednictvím COM `IConnectionPoint` rozhraní.  
  
> [!NOTE]
>  Tento model nelze zaměňovat s `IDebugProgramCreateEvent2` rozhraní, které se odesílají DE později.  
  
 Společně s událostí rozhraní samotné, odešle port [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md), [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md), a [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, které představují port, zpracování, a v uvedeném pořadí programu. Volání SDM [IDebugProgram2::GetEngineInfo](../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md) získat identifikátor GUID DE, který můžete ladit program. Identifikátor GUID byl původně získaný [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní.  
  
 SDM kontroluje, zda je DE je na seznamu povolených DEs. SDM získá tento seznam z nastavení active programu na řešení, původně předaný balíček ladění. DE musí být v seznamu povolených, jinak nebude se připojit k programu.  
  
 Jakmile je identita DE známá, SDM je připraven k připojení k programu.  
  
## <a name="see-also"></a>Viz také  
 [Spuštění programu](../../extensibility/debugger/launching-a-program.md)   
 [Připojení po spuštění](../../extensibility/debugger/attaching-after-a-launch.md)   
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)