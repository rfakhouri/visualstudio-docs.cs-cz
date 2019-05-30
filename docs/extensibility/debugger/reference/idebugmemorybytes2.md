---
title: IDebugMemoryBytes2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryBytes2
helpviewer_keywords:
- IDebugMemoryBytes2 interface
ms.assetid: d7647575-0e06-4190-88f5-ca40b82209a4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b7496c7fb083558cec08bfc851f96075ea02bae9
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347118"
---
# <a name="idebugmemorybytes2"></a>IDebugMemoryBytes2
Toto rozhraní představuje počet bajtů paměti.

## <a name="syntax"></a>Syntaxe

```
IDebugMemoryBytes2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní k reprezentaci bajtů v paměti.

## <a name="notes-for-callers"></a>Poznámky pro volající
- [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md) vrátí toto rozhraní můžete poskytnout přístup k systémové paměti. [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md) a [GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md) vrátit toto rozhraní pro poskytnutí přístupu k objektu bajtů.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugMemoryBytes2`.

|Metoda|Popis|
|------------|-----------------|
|[ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)|Načte posloupnost bajtů, spouští se v daném umístění.|
|[WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)|Zapíše `dwCount` bajtů počínaje `pStartContext`.|
|[GetSize](../../../extensibility/debugger/reference/idebugmemorybytes2-getsize.md)|Získá velikost v bajtech paměti reprezentovaný tímto rozhraním.|

## <a name="remarks"></a>Poznámky
 Pro vlastnosti [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) poskytuje rozhraní představující pole `IDebugMemoryBytes2` rozhraní pro přístup k hodnoty v tomto poli.

 Visual Studio **zobrazení paměti** volání [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md) k načtení `IDebugMemoryBytes2` rozhraní pro přístup k systémové paměti. Získat adresu přístup k analýze výrazu zadat jako adresu do zobrazení paměti a vyhodnotíte analyzovaný výraz pomocí [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) zobrazíte `IDebugProperty2` rozhraní. Volání [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) vrátí [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) adresa paměti, který popisuje. Tento kontext paměti je pak předán [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) a [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md)
- [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)
- [GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md)
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)