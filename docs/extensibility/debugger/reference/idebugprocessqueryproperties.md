---
title: IDebugProcessQueryProperties | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessQueryProperties
ms.assetid: ce29a248-81a0-42c0-99a7-1606e8c548ec
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e54c51e4012bf129e7f8a8ad44fac8dca3e888c1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917512"
---
# <a name="idebugprocessqueryproperties"></a>IDebugProcessQueryProperties
Toto rozhraní je implementováno rozhraní rozšíření [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) implementátory. To umožňuje implementátora informace o prostředí ladění procesu.

## <a name="syntax"></a>Syntaxe

```
IDebugProcessQueryProperties: IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Implementujte toto rozhraní se získat informace o prostředí pro spuštění ladění procesu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugProcessQueryProperties`.

|Metoda|Popis|
|------------|-----------------|
|[QueryProperty](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperty.md)|Dotazy na hodnotu vlastnosti.|
|[QueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperties.md)|Dotazy pro hodnoty vlastnosti.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní je implementováno zřídka.

## <a name="requirements"></a>Požadavky
 Záhlaví: Portpriv.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)