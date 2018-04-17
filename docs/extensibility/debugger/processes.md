---
title: Procesy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 75230740e84bb6660629b38e84df56fa8e5c1856
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="processes"></a>Procesy
Z hlediska architektuře ladicího programu **proces**:  
  
-   Je kontejner pro sadu programy. Je úzce podobá procesu systému Windows, který je kontejner pro sadu vláken.  
  
-   Lze identifikovat podle názvu, identifikátor nebo identifikátor fyzické.  
  
-   Můžete vytvořit výčet všechny spuštěné programy (a jejich vláken).  
  
-   Můžete popsat samostatně, port, který běží v a na počítač, který jej obsahuje.  
  
-   Můžete vytvořit jeden nebo více programů, některé z aplikací, který vytváří ukončení nebo způsobit, že program k zastavení.  
  
-   Je reprezentována [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) rozhraní, která je vytvořena při spuštění procesu. Proces se spustí správce buď relace ladění (SDM) nebo [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 Balíček ladění lze připojit modul ladění (DE) do procesu voláním [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md). To znamená, že je DE připojí všechny možné programy spuštěné v procesu, který může zpracovat. Například pokud modul common language runtime DE připojí k procesu, přiloží jenom pro programy, které běží spravovaného kódu.  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Vláken](../../extensibility/debugger/threads.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [Ladění balíčku](../../extensibility/debugger/debug-package.md)   
 [Ladění modulu](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md)