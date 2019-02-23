---
title: IDebugModule3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3
helpviewer_keywords:
- IDebugModule3 interface
ms.assetid: 44f8e96e-9c59-4ffc-9a08-9c908a0e4de7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 98b506c11ef126d0179b198336e8d969c4eec267
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56721287"
---
# <a name="idebugmodule3"></a>IDebugModule3
Toto rozhraní představuje modul, který podporuje alternativní umístění symbolů a JustMyCode stavy.

## <a name="syntax"></a>Syntaxe

```
IDebugModule3 : IDebugModule2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní pro podporu alternativního umístění symbolů a pro práci s stavy JustMyCode (najdete v článku [Glosář ladicího programu Visual Studio](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md) definici "JustMyCode").

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [getsymbolsearchinfo –](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md) vrátí toto rozhraní. DE odešle [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) rozhraní při použití Správce ladění relace (SDM) [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) metoda. Kromě toho volání [QueryInterface](/cpp/atl/queryinterface) na [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) rozhraní vrátí toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod na [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) rozhraní, toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)|Vrátí seznam hodnot cest hledá symboly a výsledky hledání jednotlivé cesty.|
|[LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)|Načte a inicializuje symbolů pro aktuální modul.|
|[IsUserCode](../../../extensibility/debugger/reference/idebugmodule3-isusercode.md)|Vrátí příznak určující, zda modul představuje uživatelského kódu.|
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugmodule3-setjustmycodestate.md)|Určuje, zda modul by měl být považováno za uživatelského kódu nebo ne.|

## <a name="remarks"></a>Poznámky
 Visual Studio je typické příjemce toto rozhraní.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)
- [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)