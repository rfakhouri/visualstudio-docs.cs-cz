---
title: IDebugModule2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2
helpviewer_keywords:
- IDebugModule2 interface
ms.assetid: 24c2a126-f4ab-4891-8509-8ef99b994c08
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a6d2e7ae091964cd810acfcddcc4ea5ab81943c4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62872839"
---
# <a name="idebugmodule2"></a>IDebugModule2
Toto rozhraní představuje modul – to znamená, spustitelný soubor částí programu, například knihovny DLL.

## <a name="syntax"></a>Syntaxe

```
IDebugModule2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní k reprezentaci modulu a poskytují přístup k informacím o tomto modulu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [getmodule –](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md) vrátí toto rozhraní. DE odešle [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md) rozhraní při použití Správce ladění relace (SDM) [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) metoda.

 Toto rozhraní může být také vrácen v [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) strukturu (který je vrácen voláním [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)).

- [Další](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md) také vrátí hodnotu toto rozhraní ([enummodules –](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) vrátí [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md) rozhraní).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugModule2`.

|Metoda|Popis|
|------------|-----------------|
|[GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)|Získá [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) tento modul, který popisuje.|
|[ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md)|ZASTARALÉ. NEPOUŽÍVEJTE. Znovu načte symboly pro tento modul.|

## <a name="remarks"></a>Poznámky
 Informace o modulu lze zobrazit **moduly** okno integrovaného vývojového prostředí.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)
- [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)
- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)
- [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)