---
title: Odesílání událostí požadované | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], required events
ms.assetid: 08319157-43fb-44a9-9a63-50b919fe1377
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: deeffb814dacc58b1fb3a3f993203139d9b1a081
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126167"
---
# <a name="sending-the-required-events"></a>Odesílání požadované událostí
Pomocí tohoto postupu pro odesílání požadované události.  
  
## <a name="process-for-sending-required-events"></a>Proces odesílání požadované událostí  
 Tyto události jsou povinné, v tomto pořadí, při vytváření ladění modul (DE) a připojíte ho k programu:  
  
1.  Odeslat [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) objekt události pro relaci ladění správce (SDM) při inicializaci DE pro ladění jeden nebo více programů v procesu.  
  
2.  Po připojení k programu chcete ladit, odeslání [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událostí objekt, který chcete SDM. Tato událost může být zastavení událostí, v závislosti na návrh vašeho modulu.  
  
3.  Pokud program je připojen k při spuštění procesu, pošlete [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) událostí objekt, který chcete SDM oznámit rozhraní IDE nové vlákno. Tato událost může být zastavení událostí, v závislosti na návrh vašeho modulu.  
  
4.  Odeslat [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) událostí objekt, který chcete SDM, pokud je program laděné dokončení načítání nebo po dokončení připojení k programu. Tato událost je třeba zastavit událostí.  
  
5.  Pokud chcete ladit je aplikace spuštěna, pošlete [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) událostí objekt, který chcete SDM při první pokyn kódu v architektuře běhu je provést. Tato událost je vždy zastavení událostí. Když zanoříte se do relace ladění, rozhraní IDE zastaví na tuto událost.  
  
> [!NOTE]
>  Mnoho jazyky použít globální inicializátory nebo externí, předkompilovaných funkce (z knihovny CRT nebo _Main) na začátku svůj kód. Pokud jazyku aplikace, kterou ladíte obsahuje některý z těchto typů elementů před počáteční vstupní bod, je-li spustit tento kód a vstupního bodu událost je odeslána při vstup uživatele bod, jako například **hlavní** nebo `WinMain`, je dosaženo.  
  
## <a name="see-also"></a>Viz také  
 [Povolení ladění programu](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)