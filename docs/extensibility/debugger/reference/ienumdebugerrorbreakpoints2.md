---
title: IEnumDebugErrorBreakpoints2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2
ms.assetid: ffdad73d-969a-45ef-9ad1-7f5d3b814018
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 568257f3ffb38329a95499815e8d7853a2fdb19f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62914744"
---
# <a name="ienumdebugerrorbreakpoints2"></a>IEnumDebugErrorBreakpoints2
Toto rozhraní zobrazí chyba zarážky přidružené čekající zarážkou.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugErrorBreakpoints2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní jako součást jeho podporu pro zarážky.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Visual Studio volání [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md) získat toto rozhraní představující seznam zarážky, které nemůže být vázán, nebo [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) získat toto rozhraní představující seznam zarážky které nejsou vázány.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugErrorBreakpoints2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-next.md)|Načte zadaný počet Chyba zarážky v sekvenci výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-skip.md)|Vynechá zadaný počet Chyba zarážky v sekvenci výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-getcount.md)|Získá počet Chyba zarážky v enumerátor.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní obsahuje seznam [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) rozhraní, z nichž každý popisuje zarážku nebylo možné svázat a proč ho nebylo možné svázat. Visual Studio používá `IEnumDebugErrorBreakpoint2` rozhraní aktualizovat zarážky uvedené v integrovaném vývojovém prostředí.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)
- [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
- [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)