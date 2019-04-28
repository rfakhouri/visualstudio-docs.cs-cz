---
title: IDebugStepCompleteEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStepCompleteEvent2
helpviewer_keywords:
- IDebugStepCompleteEvent2 interface
ms.assetid: eba2b76e-f90d-486b-ae5c-c47f1b8ba2e5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2be6568e84157c8d042113fe6f2f86b2cf288005
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62868636"
---
# <a name="idebugstepcompleteevent2"></a>IDebugStepCompleteEvent2
Toto rozhraní je odesílat pomocí ladicího stroje (DE) Správce ladění relace (SDM) po dokončení laděnému programu krokování s vnořením, krok přes nebo kroku přesahující zdrojový kód nebo příkazu nebo instrukce.

## <a name="syntax"></a>Syntaxe

```
IDebugStepCompleteEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní Oznámit dokončení operace kroku. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt události Oznámit dokončení operace kroku. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který je poskytnut pomocí SDM, když je připojen k laděnému programu.

## <a name="remarks"></a>Poznámky
 Po dokončení kroku laděnému programu je pozastavená ještě jednou a rozhraní IDE aktualizuje všechna jeho okna.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)