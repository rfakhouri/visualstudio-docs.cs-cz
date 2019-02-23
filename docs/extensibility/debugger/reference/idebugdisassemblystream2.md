---
title: IDebugDisassemblyStream2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2
helpviewer_keywords:
- IDebugDisassemblyStream2 interface
ms.assetid: b03cab0c-3f0b-4cc6-88dc-acb3b48c567a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 352d0c71151a7c99822f5ad9f15250c47541fb19
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56705817"
---
# <a name="idebugdisassemblystream2"></a>IDebugDisassemblyStream2
Toto rozhraní představuje datový proud instrukcí.

## <a name="syntax"></a>Syntaxe

```
IDebugDisassemblyStream2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj implementuje toto rozhraní pro podporu zpětného překladu kódu programu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) metoda vrátí toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugDisassemblyStream2`.

|Metoda|Popis|
|------------|-----------------|
|[Read](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)|Přečte pokyny od aktuální pozice v datovém proudu zpětný překlad.|
|[Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)|Přesune ukazatel čtení ve službě stream zpětný překlad daný počet instrukcí vzhledem k zadané pozici.|
|[GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)|Vrátí identifikátor umístění kódu pro kontext kódu.|
|[GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)|Vrátí objekt kontextu kód odpovídající identifikátor umístění zadaného kódu.|
|[GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)|Vrátí identifikátor umístění kódu, který představuje aktuální umístění v kódu.|
|[GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)|Získá zdrojový dokument přidružené k tento datový proud zpětný překlad.|
|[GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)|Získá obor tohoto datového proudu zpětný překlad.|
|[GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)|Získá velikost tohoto datového proudu zpětný překlad.|

## <a name="remarks"></a>Poznámky
 K reprezentaci celého adresního prostoru nebo jen funkce nebo modulu v prostoru lze vytvořit datový proud zpětný překlad. Každou instrukci je reprezentována [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktura vrácený voláním [čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) metoda.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)
- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)