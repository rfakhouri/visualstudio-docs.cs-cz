---
title: Procesy | Dokumentace Microsoftu
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
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 37aa4436baa449e702d5cb6f76078b2bb36311fd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675039"
---
# <a name="processes"></a>Procesy
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [procesy](https://docs.microsoft.com/visualstudio/extensibility/debugger/processes).  
  
Z hlediska architektury ladicího programu **procesu**:  
  
-   Je kontejner pro sadu aplikací. Je úzce analogické k procesu Windows, což je kontejner pro sadu vláken.  
  
-   Můžete identifikovat podle názvu, identifikátor nebo identifikátor fyzické.  
  
-   Můžete zobrazit výčet všechny spuštěné programy (a jejich vláken).  
  
-   Můžete popsat samostatně, port, který běží v a na počítač, který jej obsahuje.  
  
-   Můžete vytvořit jednu nebo další programy, ukončit libovolného z programů, které vytvoří nebo způsobit zastavení programu.  
  
-   Je reprezentován [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) rozhraní, který je vytvořen při spuštění procesu. Spustí proces buď relaci ladění správci nebo [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
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

