---
title: IDebugWindowsComputerPort2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugWindowsComputerPort2 interface
ms.assetid: 25f327b8-0303-4268-88d1-74df630436aa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9126d7507f47852b7fc9bcd3777b112932892bb4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56702145"
---
# <a name="idebugwindowscomputerport2"></a>IDebugWindowsComputerPort2
Umožňuje dotazování na informace o cílovém počítači.

## <a name="syntax"></a>Syntaxe

```
IDebugWindowsComputerPort2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní je implementováno port objekty správce ladění relace.

## <a name="methods"></a>Metody
 V následující tabulce jsou uvedeny metody objektu `IDebugWindowsComputerPort2`.

|Metoda|Popis|
|------------|-----------------|
|[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)|Načte informace o počítači, na kterém běží v ladicím programu.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll