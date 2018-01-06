---
title: Programy | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], programs
- programs, debugging
ms.assetid: e1f955d8-95da-493b-837e-e97741a26d7e
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 03b4885e653d879e3aaec1d9a68bc9be144cb676
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="programs"></a>Programy
Z hlediska architektuře ladicího programu **program**:  
  
-   Je kontejner pro sadu vláken a sadu moduly. Program nemá žádné jednoho analogie v operačním systému Windows.  
  
     Druh podproces je program. Například při ladění webu, můžete zobrazit skriptu jako programu. Zatímco skript se spustí v procesu skriptovací stroje, nezávisle na jiné skripty, má také vlastní sadu vláken. Modul ladění (DE) připojí programu a ne k procesu nebo vlákna.  
  
-   Můžete určit samostatně a proces běží v a lze k se odpojit od a popisují DE, který byl vytvořen, pokud existuje. Program lze spustit, zastavit, pokračovat a ukončen.  
  
-   Můžete vytvořit výčet všech podprocesů. Program můžete také zadat vlastní datový proud zpětný překlad a můžete vytvořit výčet všech kontextů kód z daného dokumentu pozice.  
  
-   Je reprezentována [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, vytvořili předtím, než je připojen programu, nebo jako součást procesu připojování, v závislosti na implementaci. Pokud port zobrazí programy procesu, vytvoří se každý program v souladu s odpovídající [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní předat jako argument k [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Při ladění moduly taky vytvořit `IDebugProgram2` rozhraní představují programy, tyto programy nejsou vytvářena v souladu s uzlem programu. `IDebugProgramNode2` Rozhraní vytvořené Zavedenými se používají pro skutečné ladění při nebyla vytvořena v port se používají pouze pro zjišťování, které programy běží v procesu.  
  
## <a name="see-also"></a>Viz také  
 [Procesy](../../extensibility/debugger/processes.md)   
 [Program uzly](../../extensibility/debugger/program-nodes.md)   
 [Moduly](../../extensibility/debugger/modules.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [Ladění modulu](../../extensibility/debugger/debug-engine.md)   
 [Pozice dokumentu](../../extensibility/debugger/document-position.md)   
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)