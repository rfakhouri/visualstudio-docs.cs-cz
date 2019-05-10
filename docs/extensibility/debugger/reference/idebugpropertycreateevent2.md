---
title: IDebugPropertyCreateEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPropertyCreateEvent2
helpviewer_keywords:
- IDebugPropertyCreateEvent2 interface
ms.assetid: 33b3082b-a42e-488a-a1e4-dadf506f922c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 31764e62f53304d30305f8326c6ab887ffa69e53
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457512"
---
# <a name="idebugpropertycreateevent2"></a>IDebugPropertyCreateEvent2
Toto rozhraní je odesílat pomocí ladicího stroje (DE) Správce ladění relace (SDM) při vytváření vlastnost, která souvisí s určitým dokumentem.

## <a name="syntax"></a>Syntaxe

```
IDebugPropertyCreateEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní oznamuje, zda byl vytvořen vlastností. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní. Toto rozhraní je implementováno, pokud je DE vytvořil vlastnost přidružený ke skriptu, který byl načten nebo vytvořen a tento skript je potřeba se zobrazí v integrovaném vývojovém prostředí.

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt událostí do sestavy, kterou vytvořil vlastnost. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který je poskytnut pomocí SDM, když je připojen k laděnému programu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody `IDebugPropertyCreateEvent2` rozhraní.

|Metoda|Popis|
|------------|-----------------|
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md)|Získá novou vlastnost.|

## <a name="remarks"></a>Poznámky
 Pokud je vlastnost konkrétním dokumentu nebo skriptu, které s ním spojená, DE můžete odeslat tuto událost SDM za účelem aktualizace **dokumenty skriptu** okno s názvem dokumentu. Zavolá SDM [GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md) s argumentem `guidDocument` k načtení `VARIANT` obsahující [IUnknown](/cpp/atl/iunknown) ukazatele. Zavolá SDM [QueryInterface](/cpp/atl/queryinterface) na tento ukazatel k načtení [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní, které slouží k aktualizaci **dokumenty skriptu** okna.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)