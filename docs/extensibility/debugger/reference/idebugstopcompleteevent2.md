---
title: IDebugStopCompleteEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 39da50c17d4d4b8b02390e0d2960d5696b93b1f2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53932888"
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