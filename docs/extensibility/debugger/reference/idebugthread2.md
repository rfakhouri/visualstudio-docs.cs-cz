---
title: IDebugThread2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2
helpviewer_keywords:
- IDebugThread2 interface
ms.assetid: 221b4b1b-4a26-466e-bc29-5eff800fab13
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9dcb50f732d4c7aae94cf32036cd17340d636dd9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62868356"
---
# <a name="idebugthread2"></a>IDebugThread2
Toto rozhraní představuje vlákno spuštěné v programu.

## <a name="syntax"></a>Syntaxe

```
IDebugThread2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní k reprezentaci vlákno provádění v jediném programu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [getthread –](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md) získat toto rozhraní představující aktivní vlákno.

 Toto rozhraní se také používá při vytvoření žádosti zarážky (viz [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)).

 Toto rozhraní je také vrácen při překladu mez nebo Chyba zarážky (viz [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) a [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugThread2`.

|Metoda|Popis|
|------------|-----------------|
|[EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)|Načte seznam rámce zásobníku pro toto vlákno.|
|[GetName](../../../extensibility/debugger/reference/idebugthread2-getname.md)|Získá název vlákna.|
|[SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)|Nastaví název vlákna.|
|[GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)|Získá program, ve kterém je spuštěn podproces.|
|[CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)|Určuje, zda lze nastavit další příkaz ke kontextu daného zásobník snímků a kód.|
|[SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)|Nastaví další příkaz na daném zásobníku rámce a kód kontextu.|
|[GetThreadId](../../../extensibility/debugger/reference/idebugthread2-getthreadid.md)|Získá identifikátor systému.|
|[Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)|Pozastaví vlákno.|
|[Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)|Obnoví vlákno.|
|[GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)|Získá vlastnosti, které popisují vlákno.|
|[GetLogicalThread](../../../extensibility/debugger/reference/idebugthread2-getlogicalthread.md)|Získá logické vlákno přidružené k této fyzické vlákno.|

## <a name="remarks"></a>Poznámky
 Vzhledem k tomu, že jedno fyzické vlákno lze spustit ve více programech, více než jedna `IDebugThread2` z více než jeden program může představovat stejné fyzické vlákno.

 Pokud dojde k zarážky nebo výjimky, události odesílají volání [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md). Jeden z argumentů této metodě je `IDebugThread2` rozhraní představující aktuální vlákno. [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) slouží k získání [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní pro aktuální rámec zásobníku.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
- [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)