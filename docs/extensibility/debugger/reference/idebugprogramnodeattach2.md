---
title: IDebugProgramNodeAttach2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNodeAttach2
helpviewer_keywords:
- IDebugProgramNodeAttach2 interface
ms.assetid: 46b37ac9-a026-4ad3-997b-f19e2f8deb73
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0d42b204ee0c36bc4c006704e663f41c87a83a60
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66325158"
---
# <a name="idebugprogramnodeattach2"></a>IDebugProgramNodeAttach2
Umožňuje programu uzel upozornit pokus o připojení k programu přidružené.

## <a name="syntax"></a>Syntaxe

```
IDebugProgramNodeAttach2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní je implementováno ve stejné třídě, který implementuje [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní, aby bylo možné přijímat oznámení pro operace připojení a poskytnout možnost zrušit operaci připojení.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Získat po zavolání tohoto rozhraní `QueryInterface` metodu [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objektu. [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda musí být volána před provedením [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda poskytnout uzel programu příležitost k zastavení procesu připojování.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Toto rozhraní implementuje následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)|Připojí se k programu přidružené nebo odloží procesu připojování k [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metody.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní je upřednostňovaná alternativa k zastaralá [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md) metody. Všechny ladicí stroj jsou vždy načteno s `CoCreateInstance` funkce, to znamená, že vytvořena instance mimo Adresní prostor laděného programu.

 Pokud předchozí provádění `IDebugProgramNode2::Attach_V7` metody se jednoduše nastavení `GUID` z laděného programu, pak pouze [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda musí být implementována.

 Pokud předchozí provádění `IDebugProgramNode2::Attach_V7` metoda používá rozhraní zpětného volání, která byla k dispozici a potřeba přesunout do implementace, které tuto funkci [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda a `IDebugProgramNodeAttach2` rozhraní nepodporuje musí být implementována.

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
- [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)
- [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)