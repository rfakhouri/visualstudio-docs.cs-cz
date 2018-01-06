---
title: Procesy | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e69270c5d90c26cf653ee31b81bcb9f453b814e1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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