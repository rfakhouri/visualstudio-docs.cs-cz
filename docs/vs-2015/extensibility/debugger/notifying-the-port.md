---
title: Upozornění portu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, notification
ms.assetid: f9fce48e-7d4e-4627-a0fb-77b75428146a
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 81b27b4da563c01c809203690c05702530f58416
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629844"
---
# <a name="notifying-the-port"></a>Upozornění portu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [upozornění portu](https://docs.microsoft.com/visualstudio/extensibility/debugger/notifying-the-port).  
  
Po spuštění programu, port, který musí být upozorněn, následujícím způsobem:  
  
1.  Když port obdrží nový uzel programu, odešle událost vytvoření programu zpět do relace ladění. Událost provede s ní rozhraní, které představuje program.  
  
2.  Relace ladění dotazů pro identifikátor ladicího stroje (DE), který může připojit k programu.  
  
3.  Kontroluje, jestli DE je na seznamu povolených DEs pro daný program relace ladění. Ladicí relaci získá tento seznam z nastavení aktivní program řešení, původně předána do ní balíček ladění.  
  
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
  
## <a name="see-also"></a>Viz také  
 [Spuštění programu](../../extensibility/debugger/launching-a-program.md)   
 [Připojení po spuštění](../../extensibility/debugger/attaching-after-a-launch.md)   
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)

