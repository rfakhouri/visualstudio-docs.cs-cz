---
title: IDebugMemoryContext2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2
helpviewer_keywords:
- IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bb1abe29a915d8ca2aaba1135d2e57946250bc3f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346976"
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
Toto rozhraní představuje pozici v adresním prostoru v daném počítači používají laděnému programu.

## <a name="syntax"></a>Syntaxe

```
IDebugMemoryContext2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní představující adresu v paměti.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) nebo [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md) vrátí toto rozhraní. Navíc volání [přidat](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md) a [odečíst](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md) vrátí nové kopie tohoto rozhraní po použití odpovídající aritmetické operace.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugMemoryContext2`.

|Metoda|Popis|
|------------|-----------------|
|[GetName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|Získá uživatele zobrazitelné název pro tento kontext.|
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|Získá informace popisující kontext.|
|[Add](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|Přidá zadanou hodnotu na aktuální kontext adresu a vytvoří nový kontext.|
|[Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|Odečte zadanou hodnotu z aktuálního kontextu adresu, která vytvoří nový kontext.|
|[Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|Porovná dvě kontexty způsobem indikován porovnání příznaky.|

## <a name="remarks"></a>Poznámky
 Visual Studio **paměti** volání okno [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) získat `IDebugMemoryContext2` rozhraní, které obsahuje vyhodnocený výraz použitý pro adresu paměti. Tento kontext je pak předán [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) a [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md) zadat adresu pro čtení nebo zápis.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)
- [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)
- [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)
- [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)