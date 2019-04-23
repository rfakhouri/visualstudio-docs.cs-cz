---
title: Vlákna | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5d931568258099fa4a8fe8f3b82d3fe50d5a3e35
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60099765"
---
# <a name="threads"></a>Vlákna
V architektuře ladicího programu *vlákno*:

- Je základní jednotka výpočtu. Vlákno spouští postupně jeho instrukce v rámci jednoho volání zásobníku, přechod z jednoho kódu kontextu na další.

- Můžete identifikovat samostatně a program, který běží v. Vlákna můžete s názvem, pozastavit a obnovit. Vlákno můžete také zobrazit výčet jeho přidružené zásobníku a za určitých podmínek, lze přesunout do jiného zásobníku. Zadaný kontext rámec zásobníku, vlákno může vrátit jeho přidružené logické vlákno, pokud existuje. Vlákno má vlastnosti, jako je například pozastavení počet, který lze zobrazit v **vlákna** okno integrovaného vývojového prostředí.

- Je reprezentován [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) rozhraní, obvykle vytvoří pomocí ladicího stroje (DE) nebo virtuální počítač v důsledku spuštění programu.

## <a name="see-also"></a>Viz také:
- [Programy](../../extensibility/debugger/programs.md)
- [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)
- [Ladicí stroj](../../extensibility/debugger/debug-engine.md)
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)