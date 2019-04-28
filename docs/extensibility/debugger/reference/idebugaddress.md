---
title: IDebugAddress | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress
helpviewer_keywords:
- IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7b9aba2be92516bab86f39eee55a3df4586eb09c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877775"
---
# <a name="idebugaddress"></a>IDebugAddress
Toto rozhraní představuje adresu položky. Vrátí obslužnou rutinu symbol.

## <a name="syntax"></a>Syntaxe

```
IDebugAddress : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Poskytovatel symbolů implementuje toto rozhraní představující adresu objektu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Mnoho metod na mnoho rozhraní vrátí toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Toto rozhraní implementuje následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|Načte [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura popisující objekt a jeho umístění.|

## <a name="remarks"></a>Poznámky
 Poskytovatel symbolů vrátí toto rozhraní k reprezentaci objektu a jeho umístění v rámci určitého oboru (například funkce, metody nebo třídy). Toto rozhraní je vrácená z a do různých metod poskytovatel symbolů a výraz Chyba při vyhodnocování. Za normálních okolností poskytovatel symbolů je pouze entity, které je potřeba interpretovat obsah tohoto rozhraní.

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)