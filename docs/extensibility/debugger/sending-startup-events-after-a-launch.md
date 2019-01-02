---
title: Odesílání událostí spuštění po spuštění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], startup events
ms.assetid: 306ea0b4-6d9e-4871-8d8d-a4032d422940
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: caa9f615c6ed6f314695b195a6095d238382a4c2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967494"
---
# <a name="send-startup-events-after-a-launch"></a>Odesílání událostí spuštění po spuštění
Jakmile ladicího stroje (DE) je připojen k programu, odesílá řadu událostí spuštění zpět do relace ladění.  
  
 Po spuštění událostí odeslaných zpět do relace ladění patří:  
  
- Engine vytvoření události.  
  
- Událost vytvoření programu.  
  
- Vlákno, vytváření a události načtení modulu.  
  
- Načíst událost dokončení, odeslali kód je načten a připravené ke spuštění, ale před provedením jakéhokoli kódu. 
  
  > [!NOTE]
  >  Při této události pokračuje, globální proměnné jsou inicializovány a spusťte po spuštění rutiny.  
  
- Možný další vlákno, vytváření a události načtení modulu.  
  
- Vstupní bod událost, která signalizuje, že program bylo dosaženo hlavní vstupní bod, jako například **hlavní** nebo `WinMain`. Tato událost se neposílají obvykle Pokud DE připojí k programu, který je již spuštěna.  
  
  Prostřednictvím kódu programu, DE poprvé odešle Správce ladění relace (SDM) [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) rozhraní, které představuje událost engine vytvoření, za nímž následuje [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) , která představuje událost vytvoření programu.  
  
  Tyto události jsou obvykle následovaného jednou nebo více [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) události vytváření vláken a [IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md) události načtení modulu.  
  
  Pokud kód je načten a připravené ke spuštění, ale před spuštěním jakéhokoli kódu, DE odešle SDM [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) událost dokončení zatížení. Nakonec, pokud dosud není spuštěn program, DE odešle [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) vstupní bod události, signalizaci, že program dosáhla jeho hlavní vstupní bod a je připravený k ladění.  
  
## <a name="see-also"></a>Viz také:  
 [Řízení spouštění](../../extensibility/debugger/control-of-execution.md)   
 [Ladění úloh](../../extensibility/debugger/debugging-tasks.md)