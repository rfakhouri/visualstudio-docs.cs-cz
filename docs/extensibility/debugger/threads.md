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
ms.openlocfilehash: b15928e10d77a10d9ae8b2b684af02e3b370ce87
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716009"
---
# <a name="threads"></a>Vlákna
V architektuře ladicího programu *vlákno*:

-   Je základní jednotka výpočtu. Vlákno spouští postupně jeho instrukce v rámci jednoho volání zásobníku, přechod z jednoho kódu kontextu na další.

-   Můžete identifikovat samostatně a program, který běží v. Vlákna můžete s názvem, pozastavit a obnovit. Vlákno můžete také zobrazit výčet jeho přidružené zásobníku a za určitých podmínek, lze přesunout do jiného zásobníku. Zadaný kontext rámec zásobníku, vlákno může vrátit jeho přidružené logické vlákno, pokud existuje. Vlákno má vlastnosti, jako je například pozastavení počet, který lze zobrazit v **vlákna** okno integrovaného vývojového prostředí.

-   Je reprezentován [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) rozhraní, obvykle vytvoří pomocí ladicího stroje (DE) nebo virtuální počítač v důsledku spuštění programu.

## <a name="see-also"></a>Viz také:
- [Programy](../../extensibility/debugger/programs.md)
- [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)
- [Ladicí stroj](../../extensibility/debugger/debug-engine.md)
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)