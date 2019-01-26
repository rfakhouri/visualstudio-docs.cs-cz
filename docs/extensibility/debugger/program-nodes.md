---
title: Program uzly | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- program nodes, debugging context
- debugging [Debugging SDK], program nodes
- program nodes, adding
- program nodes, superceding
ms.assetid: 1c5a5c13-c14d-42c3-af11-4c63f1032c8d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 61e09651786870d892eaa85a01561ddb283785bf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54921892"
---
# <a name="program-nodes"></a>Uzly programů
V architektuře ladicího programu *program uzel*:  
  
- Představuje jednoduchý popis programu.  
  
- Můžete identifikovat samostatně a běží v procesu. Uzel program lze připojit k, být odpojen od a popisují ladicího stroje (DE), který byl vytvořen, pokud existuje.  
  
- Je reprezentován [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní, obvykle vytváří DE nebo portu. Uzly programů jsou přidána na port voláním [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Když program uzel se přidá k portu, přidá se do procesu obsahující program, který představuje tento uzel programu.  
  
  Nějakou dobu, po spuštění relace ladění, v závislosti na implementaci balíček ladicí program uzly slouží k vytvoření odpovídající programy. Když je proces pro jeho programy, jsou uvedené programy, jeden pro každý uzel programu.  
  
  Než programu přiřazen, rozhraní IDE potřebuje jednoduchý popis programu. Tyto informace můžete získat z uzlu programu. Jakmile program je připojen k, rozhraní IDE zobrazí podrobnější informace, jako je například seznam všechna vlákna spuštěná v programu. Tyto informace se získávají z této aplikace.  
  
## <a name="see-also"></a>Viz také:  
 [Programy](../../extensibility/debugger/programs.md)   
 [Procesy](../../extensibility/debugger/processes.md)   
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)