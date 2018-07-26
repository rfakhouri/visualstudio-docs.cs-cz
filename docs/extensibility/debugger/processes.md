---
title: Procesy | Dokumentace Microsoftu
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
ms.openlocfilehash: 3c07a9cb6c16f09f2f55b543087e25d85bc300c0
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251774"
---
# <a name="processes"></a>Procesy
V architektuře ladicího programu *procesu*:  
  
-   Je kontejner pro sadu aplikací. Je úzce analogické k procesu Windows, což je kontejner pro sadu vláken.  
  
-   Můžete identifikovat podle názvu, identifikátor nebo identifikátor fyzické.  
  
-   Můžete zobrazit výčet všechny spuštěné programy (a jejich vláken).  
  
-   Můžete popsat samostatně, port, který běží v a na počítač, který jej obsahuje.  
  
-   Můžete vytvořit jednu nebo další programy, ukončit libovolného z programů, které vytvoří nebo způsobit zastavení programu.  
  
-   Je reprezentován [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) rozhraní, který je vytvořen při spuštění procesu. Spustí proces buď relaci ladění správci nebo [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 Ladění balíčku můžete připojit ladicí stroj (DE) k procesu voláním [připojit](../../extensibility/debugger/reference/idebugprocess2-attach.md), což znamená, že je DE připojí všechny možné programů spuštěných v rámci procesu, který dokáže zpracovat. Například pokud modul common language runtime DE připojí se k procesu, se připojí pouze pro programy, na kterých běží spravovaný kód.  
  
## <a name="see-also"></a>Viz také:  
 [Programy](../../extensibility/debugger/programs.md)   
 [Vlákna](../../extensibility/debugger/threads.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [Ladění balíčku](../../extensibility/debugger/debug-package.md)   
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md)