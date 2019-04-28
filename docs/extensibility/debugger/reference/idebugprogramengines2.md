---
title: IDebugProgramEngines2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEngines2
helpviewer_keywords:
- IDebugProgramEngines2 interface
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1a5ad34904a2f0bf02e5a2221f1ff73093012a41
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916927"
---
# <a name="idebugprogramengines2"></a>IDebugProgramEngines2
Toto rozhraní se používá program uzly k určení všech možných ladění motorů (DE), které můžete ladit tento program.

## <a name="syntax"></a>Syntaxe

```
IDebugProgramEngines2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Zavedenými nebo dodavatele port. Tento vlastní port implementuje toto rozhraní na stejný objekt, který implementuje [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) pro podporu vytváření konkrétní DE určený pro konkrétní aplikaci.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugProgramNode2` rozhraní k získání tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugProgramEngines2`.

|Metoda|Popis|
|------------|-----------------|
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|Označuje možné DEs, který můžete ladit tento program.|
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|Vybere DE pro ladění tohoto programu.|

## <a name="remarks"></a>Poznámky
 Jakmile Zavedenými zvolená tímto uživatelem, tato volba je zaregistrován uzel program voláním [SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md). Vybraný stroj stane modul vrácený [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
- [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)