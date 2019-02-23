---
title: INTERCEPT_EXCEPTION_ACTION | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- INTERCEPT_EXCEPTION_ACTION
helpviewer_keywords:
- INTERCEPT_EXCEPTION_ACTION enumeration
ms.assetid: e647f1eb-2932-4447-8c78-3b0d706fb972
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0cac3e4fb6c072a26ede753213f6546c2ff50afa
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723432"
---
# <a name="interceptexceptionaction"></a>INTERCEPT_EXCEPTION_ACTION
Určuje, jaká opatření je třeba provést při zachycení výjimky.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_INTERCEPT_EXCEPTION_ACTION
{
    IEA_INTERCEPT = 0x0001
}
typedef DWORD INTERCEPT_EXCEPTION_ACTION;
```

```csharp
public enum enum_INTERCEPT_EXCEPTION_ACTION
{
    IEA_INTERCEPT = 0x0001
}
```

#### <a name="parameters"></a>Parametry
IEA_INTERCEPT umožňuje zachycení na aktuální výjimku. Toto je jediná hodnota podporovaná v současné době a musí být zadán.

## <a name="remarks"></a>Poznámky
Tyto hodnoty jsou předány [interceptcurrentexception –](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)
