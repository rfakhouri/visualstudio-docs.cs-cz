---
title: Odesílání událostí spuštění po spuštění | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], startup events
ms.assetid: 306ea0b4-6d9e-4871-8d8d-a4032d422940
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: eeb378b09ffc3e12de8996d7feabbd20a4b40068
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54782925"
---
# <a name="sending-startup-events-after-a-launch"></a>Odesílání událostí spuštění po spuštění
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Jakmile ladicího stroje (DE) je připojen k programu, odesílá řadu událostí spuštění zpět do relace ladění.  
  
 Po spuštění událostí odeslaných zpět do relace ladění, patří:  
  
- Engine vytvoření události.  
  
- Událost vytvoření programu.  
  
- Vlákno, vytváření a události načtení modulu.  
  
- Událost dokončení zatížení, odeslali kód je načten a připravené ke spuštění, ale před provedením jakéhokoli kódu  
  
  > [!NOTE]
  >  Při této události pokračuje, globální proměnné jsou inicializovány a spusťte po spuštění rutiny.  
  
- Možný další vlákno, vytváření a události načtení modulu.  
  
- Vstupní bod událost, která signalizuje, že program bylo dosaženo hlavní vstupní bod, jako například **hlavní** nebo `WinMain`. Tato událost se neposílají obvykle Pokud DE připojí k programu, který je již spuštěna.  
  
  Prostřednictvím kódu programu, DE poprvé odešle Správce ladění relace (SDM) [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) rozhraní, které představuje událost engine vytvoření, za nímž následuje [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) , která představuje událost vytvoření programu.  
  
  To je obvykle následovaného jednou nebo více [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) události vytváření vláken a [IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md) události načtení modulu.  
  
  Pokud kód je načten a připravené ke spuštění, ale před spuštěním jakéhokoli kódu, DE odešle SDM [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) událost dokončení zatížení. Nakonec, pokud dosud není spuštěn program, DE odešle [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) vstupní bod události, signalizaci, že program dosáhla jeho hlavní vstupní bod a je připravený k ladění.  
  
## <a name="see-also"></a>Viz také  
 [Řízení spouštění](../../extensibility/debugger/control-of-execution.md)   
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)
