---
title: IEnumDebugPorts2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPorts2
helpviewer_keywords:
- IEnumDebugPorts2
ms.assetid: 1754eef3-cf62-42e0-b218-1911acba77d4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1741c12a7e51d08f0bd575d79e3ca789428dad0a
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225511"
---
# <a name="ienumdebugports2"></a>IEnumDebugPorts2
Toto rozhraní uvádí porty počítači nebo port dodavatele.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugPorts2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Dodavatel port. Tento vlastní port implementuje toto rozhraní představující seznam portů vytvořili dodavatelem. Visual Studio implementuje toto rozhraní podporu vlastní dodavatele portu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) získat toto rozhraní představující seznam portů, které jsou vytvořené dodavatele portu. Volání [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md) získat toto rozhraní představující seznam portů, které byly uloženy na disk.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugPorts2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugports2-next.md)|Načte zadaný počet portů v sekvenci výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugports2-skip.md)|Vynechá zadaný počet portů v sekvenci výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugports2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugports2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugports2-getcount.md)|Získá počet portů v enumerátor.|

## <a name="remarks"></a>Poznámky
 Visual Studio používá toto rozhraní k naplnění seznamu porty používané pro připojení k procesům.

 Ladicí stroj obvykle nepoužívá toto rozhraní.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)
- [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)