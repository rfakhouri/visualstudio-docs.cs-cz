---
title: IDebugStackFrame3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame3
helpviewer_keywords:
- IDebugStackFrame3 interface
ms.assetid: 39af2f57-0a01-42b8-b093-b7fbc61e2909
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0960f0f527d844afcc44947f1204db78d4d91a38
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66352060"
---
# <a name="idebugstackframe3"></a>IDebugStackFrame3
Toto rozhraní rozšiřuje [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) zpracovat zachycené výjimky.

## <a name="syntax"></a>Syntaxe

```
IDebugStackFrame3 : IDebugStackFrame2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje na stejný objekt, který implementuje toto rozhraní [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní pro podporu zachycené výjimky.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugStackFrame2` rozhraní k získání tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod zděděných z [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md), `IDebugStackFrame3` poskytuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)|Zpracovává výjimku pro aktuální rámec zásobníku před zpracování jakékoli pravidelné výjimek.|
|[GetUnwindCodeContext](../../../extensibility/debugger/reference/idebugstackframe3-getunwindcodecontext.md)|Vrátí kontext kódu, pokud dojde k odvíjení zásobníku.|

## <a name="remarks"></a>Poznámky
 Zachycené výjimky znamená, že ladicí program může zpracovat výjimku před voláním jakékoli normální obslužné rutiny jsou podle času spuštění. Zachycení výjimky v podstatě znamená, že čas spuštění předstírají, že má obslužné rutiny výjimek i v případě, že není k dispozici.

- [Interceptcurrentexception –](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) je volána v průběhu všech událostí zpětného volání normální výjimkou (jedinou výjimkou je, pokud ladění ve smíšeném režimu kódu (spravovaného a nespravovaného kódu), v takovém případě nemůže být zachycena výjimka během zpětné volání poslední odpovídající). Pokud DE neimplementuje `IDebugStackFrame3`, nebo Německo vrátí chybu z IDebugStackFrame3::`InterceptCurrentException` (například `E_NOTIMPL`), pak ladicí program bude obvykle zpracování výjimky.

 Tím, že zachytává výjimku, ladicí program umožňuje uživatelům provádět změny stavu laděného programu a potom pokračovat v provádění v místě, kde byla výjimka vydána.

> [!NOTE]
> Zachycené výjimky jsou povoleny pouze ve spravovaném kódu, tedy v programu, který běží v části Common Language Runtime (CLR).

 Ladicí stroj označuje, že ji podporuje prověřuje zachycovací výjimky tak, že nastavíte "metricExceptions" na hodnotu 1 za běhu pomocí `SetMetric` funkce. Další informace najdete v tématu [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
