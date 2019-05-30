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
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 084a386cc7d7f9c6d606e7015e593a4075ba53a9
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351429"
---
# <a name="program-nodes"></a>Uzly programů
V architektuře ladicího programu *program uzel*:

- Představuje jednoduchý popis programu.

- Můžete identifikovat samostatně a běží v procesu. Uzel program lze připojit k, být odpojen od a popisují ladicího stroje (DE), který byl vytvořen, pokud existuje.

- Je reprezentován [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní, obvykle vytváří DE nebo portu. Uzly programů jsou přidána na port voláním [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Když program uzel se přidá k portu, přidá se do procesu obsahující program, který představuje tento uzel programu.

  Nějakou dobu, po spuštění relace ladění, v závislosti na implementaci balíček ladicí program uzly slouží k vytvoření odpovídající programy. Když je proces pro jeho programy, jsou uvedené programy, jeden pro každý uzel programu.

  Než programu přiřazen, rozhraní IDE potřebuje jednoduchý popis programu. Tyto informace můžete získat z uzlu programu. Jakmile program je připojen k, rozhraní IDE zobrazí podrobnější informace, jako je například seznam všechna vlákna spuštěná v programu. Tyto informace se získávají z této aplikace.

## <a name="see-also"></a>Viz také:
- [Programy](../../extensibility/debugger/programs.md)
- [Procesy](../../extensibility/debugger/processes.md)
- [Ladicí stroj](../../extensibility/debugger/debug-engine.md)
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)
- [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)