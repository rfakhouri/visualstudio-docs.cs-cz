---
title: "Odesílání událostí spuštění po spuštění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], startup events
ms.assetid: 306ea0b4-6d9e-4871-8d8d-a4032d422940
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 65e05d7da2acf5bd3eaf8dab1e3781d3d5b244a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sending-startup-events-after-a-launch"></a>Odesílání událostí spuštění po spuštění
Jakmile modul ladění (DE) je připojen k programu, odešle řady událostí spuštění zpět na relaci ladění.  
  
 Spuštění událostí odeslaných zpět do relace ladění zahrnují následující:  
  
-   Vytvoření události modulu.  
  
-   Událost vytvoření programu.  
  
-   Přístup z více vláken vytváření a události modulu zatížení.  
  
-   Událost complete zatížení, odeslána, když kód je načíst a připravené ke spuštění, ale před provedením žádný kód  
  
    > [!NOTE]
    >  Při této události je dál, jsou inicializovány globální proměnné a spusťte spuštění rutiny.  
  
-   Možné další vlákna vytváření a události modulu zatížení.  
  
-   Vstupní bod událost, která signalizuje, že program bylo dosaženo jeho hlavní vstupní bod, jako **hlavní** nebo `WinMain`. Tato událost se neposílají obvykle, pokud je DE připojí k programu, který je již spuštěna.  
  
 Prostřednictvím kódu programu, DE poprvé odešle správce ladicí relace (SDM) [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) rozhraní, což představuje událost vytvoření modulu, za nímž následuje [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) , která představuje událost vytvoření programu.  
  
 To je obvykle následuje jeden nebo více [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) události vytváření vláken a [IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md) události modulu zatížení.  
  
 Pokud kód je načíst a připravené ke spuštění, ale předtím, než je jakýkoli kód spustí, DE odešle SDM [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) událost complete zatížení. Nakonec, pokud ještě není spuštěn program, DE odešle [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) vstupní bod událostí, signalizace, že bylo dosaženo jeho hlavní vstupní bod a je připravený pro ladění program.  
  
## <a name="see-also"></a>Viz také  
 [Řízení spouštění](../../extensibility/debugger/control-of-execution.md)   
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)