---
title: Vlákna | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8070107a1befab999f2edd47d32e25e84266b86d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666180"
---
# <a name="threads"></a>Vlákna
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vlákna](https://docs.microsoft.com/visualstudio/extensibility/debugger/threads).  
  
Z hlediska architektury ladicího programu **vlákno**:  
  
-   Je základní jednotka výpočtu. Vlákno spouští postupně jeho instrukce v rámci jednoho volání zásobníku, přechod z jednoho kódu kontextu na další.  
  
-   Můžete identifikovat samostatně a program běží a může být s názvem, pozastavit a obnovit. Vlákno můžete také zobrazit výčet jeho přidružené zásobníku a za určitých podmínek, lze přesunout do jiného zásobníku. Zadaný kontext rámec zásobníku, vlákno může vrátit jeho přidružené logické vlákno, pokud existuje. Vlákno obsahuje vlastnosti, jako je počet pozastavit, které mohou být zobrazeny v okně vlákna v integrovaném vývojovém prostředí.  
  
-   Je reprezentován [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) rozhraní, obvykle vytvoří pomocí ladicího stroje (DE) nebo virtuální počítač v důsledku spuštění programu.  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)

