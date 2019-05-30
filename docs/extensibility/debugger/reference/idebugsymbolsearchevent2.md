---
title: IDebugSymbolSearchEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolSearchEvent2
helpviewer_keywords:
- IDebugSymbolSearchEvent2
ms.assetid: 9b946d55-ff85-44eb-b40a-efbf8282eafd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ed7108c9e1349b01115bed8a6b2a77a3eaa71f45
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66320381"
---
# <a name="idebugsymbolsearchevent2"></a>IDebugSymbolSearchEvent2
Toto rozhraní je odeslaný ladicího stroje (DE) k označení, že byly načteny symboly pro ladění pro modul, který se právě ladí.

## <a name="syntax"></a>Syntaxe

```
IDebugSymbolSearchEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní oznamuje, že byly načteny symboly modulu. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt události oznamuje, že byly načteny symboly modulu. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při připojení k laděnému programu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 `IDebugSymbolSearchEvent2` Rozhraní poskytuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)|Načte informace o výsledky hledání symbolu.|

## <a name="remarks"></a>Poznámky
 Tato událost se pošle i v případě, že se nepodařilo načíst symboly. Volání `IDebugSymbolSearchEvent2::GetSymbolSearchInfo` umožňuje obslužné rutiny události k určení, pokud má modul ve skutečnosti všechny symboly.

 Visual Studio obvykle používá k aktualizaci stavu načtené symboly v této události **moduly** okna.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)