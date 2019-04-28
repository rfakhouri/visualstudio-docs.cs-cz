---
title: IDebugProcessEx2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcessEx2
helpviewer_keywords:
- IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e0b29d88387ccb2ed711f1a000bf7bb00a34dd01
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62870694"
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
Toto rozhraní umožňuje relace ladění správci upozornění procesu, který je k připojení nebo odpojení od procesu.

## <a name="syntax"></a>Syntaxe

```
IDebugProcessEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Dodavatel port. Tento vlastní port implementuje toto rozhraní na stejný objekt jako [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) rozhraní za účelem:

- Podpora sledování relací, které jsou připojené k procesu

- Podpora automatické připojení napříč více ladicími stroji

  Pokud zvolí dodavatele port. Tento vlastní port toto rozhraní implementovat.

## <a name="notes-for-callers"></a>Poznámky pro volající

- Volání SDM [QueryInterface](/cpp/atl/queryinterface) na `IDebugProcess2` rozhraní k získání tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugProcessEx2`.

|Metoda|Popis|
|------------|-----------------|
|[Attach](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|Informuje o procesu relace je nyní ladění procesu.|
|[Detach](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|Informuje o procesu relace je již ladění procesu.|
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|Přidá uzly programů seznam ladicí stroj.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní je privátní mezi SDM a procesu.

## <a name="requirements"></a>Požadavky
 Záhlaví: Portpriv.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)