---
title: IDebugQueryEngine2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugQueryEngine2
helpviewer_keywords:
- IDebugQueryEngine2 interface
ms.assetid: 8f0e1838-a818-4459-9138-a3dceb7408de
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b0254322ecccd3fb8a79ee30a10434ff130c068c
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458739"
---
# <a name="idebugqueryengine2"></a>IDebugQueryEngine2
Toto rozhraní umožňuje relace ladění správci načíst rozhraní, které představuje ladicího stroje (DE).

## <a name="syntax"></a>Syntaxe

```
IDebugQueryEngine2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní pro objekty, které implementují rozhraní nejběžnější DE (například [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md), [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md), a [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)) v pořadí pro povolení přístupu k [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) rozhraní DE samotný.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [QueryInterface](/cpp/atl/queryinterface) na typické DE rozhraní k získání tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugQueryEngine2`.

|Metoda|Popis|
|------------|-----------------|
|[GetEngineInterface](../../../extensibility/debugger/reference/idebugqueryengine2-getengineinterface.md)|Získá rozhraním vlastního ladicího stroje (DE).|

## <a name="remarks"></a>Poznámky
 Toto rozhraní je zpravidla implementovaní v objektu, který implementuje [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní za účelem podpory seřazené příčinnou souvislost krokování funkce; to znamená, když je ladicí program krokování ve funkci Další funkce pro spuštění nemusí být předchozí funkce v zásobníku, ale funkce v jiném vlákně úplně se vynechá. Definice "příčiny", najdete v článku [Glosář ladicího programu Visual Studio](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)