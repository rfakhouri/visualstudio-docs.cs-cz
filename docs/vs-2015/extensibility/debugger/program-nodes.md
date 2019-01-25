---
title: Program uzly | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- program nodes, debugging context
- debugging [Debugging SDK], program nodes
- program nodes, adding
- program nodes, superceding
ms.assetid: 1c5a5c13-c14d-42c3-af11-4c63f1032c8d
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3a06be4ef0a69ec173f171ba202f1f479448b1ca
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54775093"
---
# <a name="program-nodes"></a>Uzly programů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Z hlediska architektury ladicího programu **program uzel**:  
  
- Představuje jednoduchý popis programu.  
  
- Můžete identifikovat samostatně a proces je spuštěn v a lze připojit k být odpojen od a popisují ladicího stroje (DE), který byl vytvořen, pokud existuje.  
  
- Je reprezentován [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní, obvykle vytváří DE nebo portu. Uzly programů jsou přidána na port voláním [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Když program uzel se přidá k portu, přidá se do procesu obsahující program, který představuje tento uzel programu.  
  
  Nějakou dobu, po spuštění relace ladění, v závislosti na implementaci balíček ladicí program uzly slouží k vytvoření odpovídající programy. Když je proces pro jeho programy, jsou uvedené programy, jeden pro každý uzel programu.  
  
  Než programu přiřazen, rozhraní IDE potřebuje jednoduchý popis programu. Tyto informace můžete získat z uzlu programu. Jakmile program je připojen k, integrovaném vývojovém prostředí musí zobrazit podrobnější informace, jako je například seznam všechna vlákna spuštěná v programu. Tyto informace se získávají z této aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Procesy](../../extensibility/debugger/processes.md)   
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)
