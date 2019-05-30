---
title: IEnumDebugModules2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugModules2
helpviewer_keywords:
- IEnumDebugModules2
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bd6d7dc2cba76443d409feef4f2fe9dd0cd04e33
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66339646"
---
# <a name="ienumdebugmodules2"></a>IEnumDebugModules2
Toto rozhraní se zobrazí seznam modulů.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugModules2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní představující seznam modulů pro program.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Visual Studio volání [enummodules –](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) k získání tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugModules2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|Načte zadaný počet modulů v sekvenci výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|Vynechá zadaný počet modulů v sekvenci výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|Získá počet modulů.|

## <a name="remarks"></a>Poznámky
 Visual Studio používá toto rozhraní primárně k aktualizaci **moduly** okna.

 Pro účely ladění v sadě Visual Studio, programu je logická posloupnost kód pokyny, které lze napříč hranicemi modulu, proto potřeba seznam modulů pro jeden [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní. První modul v seznamu obvykle obsahuje počáteční vstupní bod pro přidružené aplikace.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)