---
title: Vlákna | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 028ad25495ba01d9763c8bec3bbb9c4480d72ff8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68185361"
---
# <a name="threads"></a>Vlákna
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Z hlediska architektury ladicího programu **vlákno**:  
  
- Je základní jednotka výpočtu. Vlákno spouští postupně jeho instrukce v rámci jednoho volání zásobníku, přechod z jednoho kódu kontextu na další.  
  
- Můžete identifikovat samostatně a program běží a může být s názvem, pozastavit a obnovit. Vlákno můžete také zobrazit výčet jeho přidružené zásobníku a za určitých podmínek, lze přesunout do jiného zásobníku. Zadaný kontext rámec zásobníku, vlákno může vrátit jeho přidružené logické vlákno, pokud existuje. Vlákno obsahuje vlastnosti, jako je počet pozastavit, které mohou být zobrazeny v okně vlákna v integrovaném vývojovém prostředí.  
  
- Je reprezentován [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) rozhraní, obvykle vytvoří pomocí ladicího stroje (DE) nebo virtuální počítač v důsledku spuštění programu.  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)
