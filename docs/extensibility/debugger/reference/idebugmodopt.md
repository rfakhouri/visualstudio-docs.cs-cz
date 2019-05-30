---
title: IDebugModOpt | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugModOpt interface
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d9f8fa5e496056eac2a30114f4062f635775350b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324054"
---
# <a name="idebugmodopt"></a>IDebugModOpt
Představuje volitelný modifikátor ladění.

## <a name="syntax"></a>Syntaxe

```
IDebugModOpt : IUnknown
```

## <a name="notes-for-callers"></a>Poznámky pro volající
 Získané z [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt, který reprezentuje třídy nebo metody.

## <a name="methods"></a>Metody
 Toto rozhraní implementuje následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|Načte seznam volitelné modifikátory.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll