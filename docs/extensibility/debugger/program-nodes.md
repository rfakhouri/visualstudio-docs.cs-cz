---
title: Program uzly | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- program nodes, debugging context
- debugging [Debugging SDK], program nodes
- program nodes, adding
- program nodes, superceding
ms.assetid: 1c5a5c13-c14d-42c3-af11-4c63f1032c8d
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 90ec92ad46a850c26e700e9feafa60d291f608ba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="program-nodes"></a>Program uzly
Z hlediska architektuře ladicího programu **program uzlu**:  
  
-   Je lightweight popis programu.  
  
-   Můžete určit samostatně a proces běží v a lze k se odpojit od a popisují modul ladění (DE), který byl vytvořen, pokud existuje.  
  
-   Je reprezentována [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní, obvykle vytvoří DE nebo portu. Program uzly jsou přidána na port voláním [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Když program uzlu se přidá k portu, se přidá do procesu obsahující program, který představuje tento uzel program.  
  
 Zopakovat po spuštění relace ladění, v závislosti na implementaci ladění balíčku, program uzly slouží k vytvoření odpovídající programy. Při procesu je dotazován na jeho programy, jsou uvedené programy, jednu pro každý uzel program.  
  
 Před program je připojen k, musí prostředí IDE lightweight popis programu. Tyto informace můžete získat z uzlu programu. Jakmile program je připojen k, rozhraní IDE musí zobrazit podrobnější informace, jako je například seznam všechna vlákna spuštění programu. Tyto informace se získávají z této aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Procesy](../../extensibility/debugger/processes.md)   
 [Ladění modulu](../../extensibility/debugger/debug-engine.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)