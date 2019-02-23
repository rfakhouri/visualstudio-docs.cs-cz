---
title: IEnumDebugPrograms2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPrograms2
helpviewer_keywords:
- IEnumDebugPrograms2
ms.assetid: 7fbb8fb7-db64-4546-a364-dc668430c8af
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 866b3718ac6071b5e7bd5cc44ed2ca17dd54dc8e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687638"
---
# <a name="ienumdebugprograms2"></a>IEnumDebugPrograms2
Toto rozhraní vytvoří výčet programy spuštěné v aktuální relaci ladění.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugPrograms2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní uvést seznam programů, které jsou právě laděny ve DE.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Visual Studio volání [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) získat toto rozhraní. [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md) se používá sada Visual Studio.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugPrograms2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)|Načte zadaný počet programy v sekvenci výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugprograms2-skip.md)|Vynechá zadaný počet programy v sekvenci výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugprograms2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugprograms2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprograms2-getcount.md)|Získá počet programů v enumerátor.|

## <a name="remarks"></a>Poznámky
 Visual Studio používá toto rozhraní:

-   Naplnění **moduly** okno (voláním [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) a následným voláním [enummodules –](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) v každém programu).

-   Naplnění **připojit k procesu** seznamu (voláním `IDebugProcess2::EnumPrograms` a následným voláním [QueryInterface](/cpp/atl/queryinterface) na každém [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní získat [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md) rozhraní).

-   Vygeneruje seznam DEs, který lze ladit každém programu v procesu (pomocí [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md)).

-   Použití aktualizací upravit a pokračovat (ENC) pro každý program (voláním IDebugProcess2::EnumPrograms a následným voláním [GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md)).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)
- [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)