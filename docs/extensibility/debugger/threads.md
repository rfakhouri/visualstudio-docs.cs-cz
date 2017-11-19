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
ms.openlocfilehash: 150e27c4b8df06784848829bfe713773cf9d48a0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Správce ladicí relace](../../extensibility/debugger/session-debug-manager.md)