---
title: IDebugStopCompleteEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 33272f87ae30832588a998ebea2fc46e9adaae50
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54984233"
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2

Ladicí stroj (DE) můžete odeslat této události volitelné správce ladění relace (SDM) po zastavení programu.

## <a name="syntax"></a>Syntaxe

```
IDebugStopCompleteEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory

Toto rozhraní byla zavedena v systému Visual Studio 2005. Předchozí verze nepodporuje asynchronní zastavení.

[Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) je volán SDM ve scénářích pro více procesů nebo více programů. Pokud jeden program odešle událostí ukončení SDM, SDM požádá o další programy zastavit příliš.

Zastavení je sloužící k informování asynchronně SDM, program se zastavila. Informování, je užitečné pro ladicí stroj interpretu SDM, někdy žádný kód se spuštěným uvnitř laděného programu, tak [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) nemůže být dokončena synchronně. Pokud ladicí stroj chce využívat tato asynchronní oznámení, musí vracet `S_ASYNC_STOP` z [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).

## <a name="requirements"></a>Požadavky

Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll