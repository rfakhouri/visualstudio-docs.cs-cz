---
title: IDebugPortEvents2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEvents2
helpviewer_keywords:
- IDebugPortEvents2 interface
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5690108aaeede2cf15cc5fac927a3dc5ab3855ab
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66326731"
---
# <a name="idebugportevents2"></a>IDebugPortEvents2
Toto rozhraní upozorní naslouchací proces (obvykle správce ladění relace [SDM] nebo ladicí stroj) z procesu a program vytváření a ničení na konkrétním portu. Tyto informace slouží k zobrazení v reálném čase přehled procesů a programy spuštěné na portu.

## <a name="syntax"></a>Syntaxe

```
IDebugPortEvents2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Visual Studio obvykle implementuje toto rozhraní k přijímání oznámení o program vytváření a zničení. Ladicí stroj, můžete taky implementovat toto rozhraní tak, aby naslouchala událostem těchto portů.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Všechny [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) rozhraní je možné zadávat dotazy pro <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní. Pak bude <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.FindConnectionPoint%2A> metodu `IDebugPortEvents2` je volána <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní pro získání <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní. Nakonec <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> metoda ve <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní je volána k odesílání událostí přes [události](../../../extensibility/debugger/reference/idebugportevents2-event.md) metody.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody `IDebugPortEvents2`.

|Metoda|Popis|
|------------|-----------------|
|[Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)|Odesílá události, které popisují vytváření a ničení procesy a programů na portu.|

## <a name="remarks"></a>Poznámky
 `IDebugPortEvents2` také používá SDM ladit programy, které běží v procesu, který je již laděn.

 Port události jsou předány SDM tímto rozhraním.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)