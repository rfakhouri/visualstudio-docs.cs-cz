---
title: "Vlákna | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f611284584b091fca390f660b3e840f6cebe048c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="threads"></a>Vlákna
Z hlediska architektuře ladicího programu **vlákno**:  
  
-   Je základní jednotkou výpočtu. Vlákna spustí sekvenčně jeho pokyny v rámci jednoho volání zásobníku, z kontextu jeden kód Přesun na další.  
  
-   Můžete určit samostatně a program je běží a jde s názvem, byla pozastavena a obnovit. Vlákno můžete také vytvořit výčet jeho rámce zásobníku přidružené a za určitých podmínek může přesunout na jiný rámec zásobníku. Zadaný kontext rámce zásobníku, vlákno může vrátit jeho přidružené logické vlákno, pokud existuje. Vlákno má vlastnosti, jako je například počet pozastavit, které mohou být zobrazeny v okně vláken rozhraní IDE.  
  
-   Je reprezentována [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) rozhraní, obvykle vytvoří virtuální počítač v důsledku spuštění programu nebo ladění modulu (DE).  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Ladění modulu](../../extensibility/debugger/debug-engine.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)