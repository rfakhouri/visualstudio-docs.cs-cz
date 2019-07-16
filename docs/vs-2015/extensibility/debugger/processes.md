---
title: Procesy | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 82718a7ceb7a18f9978840f35ca0c5fce5628e81
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153671"
---
# <a name="processes"></a>Procesy
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Z hlediska architektury ladicího programu **procesu**:  
  
- Je kontejner pro sadu aplikací. Je úzce analogické k procesu Windows, což je kontejner pro sadu vláken.  
  
- Můžete identifikovat podle názvu, identifikátor nebo identifikátor fyzické.  
  
- Můžete zobrazit výčet všechny spuštěné programy (a jejich vláken).  
  
- Můžete popsat samostatně, port, který běží v a na počítač, který jej obsahuje.  
  
- Můžete vytvořit jednu nebo další programy, ukončit libovolného z programů, které vytvoří nebo způsobit zastavení programu.  
  
- Je reprezentován [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) rozhraní, který je vytvořen při spuštění procesu. Spustí proces buď relaci ladění správci nebo [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
  Ladění balíčku můžete připojit ladicí stroj (DE) k procesu voláním [připojit](../../extensibility/debugger/reference/idebugprocess2-attach.md). To znamená, že DE připojí všechny možné programů spuštěných v rámci procesu, který dokáže zpracovat. Například pokud modul common language runtime DE připojí se k procesu, se připojí pouze pro programy, na kterých běží spravovaný kód.  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Vlákna](../../extensibility/debugger/threads.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [Ladění balíčku](../../extensibility/debugger/debug-package.md)   
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md)
