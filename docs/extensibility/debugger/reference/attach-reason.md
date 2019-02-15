---
title: ATTACH_REASON | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7acd5b87288365cde43b2eb8f460b52048dcf36f
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318703"
---
# <a name="attachreason"></a>ATTACH_REASON
Určuje důvod ladicího stroje (DE) k připojení k uzlu programu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_ATTACH_REASON {
    ATTACH_REASON_LAUNCH = 0x0001,
    ATTACH_REASON_USER   = 0x0002,
    ATTACH_REASON_AUTO   = 0x0003
};
typedef DWORD ATTACH_REASON;
```

```csharp
public enum enum_ATTACH_REASON {
    ATTACH_REASON_LAUNCH = 0x0001,
    ATTACH_REASON_USER   = 0x0002,
    ATTACH_REASON_AUTO   = 0x0003
};
```

## <a name="members"></a>Členové
ATTACH_REASON_AUTO  
Připojte, protože proces je aktuálně v režimu ladění.

ATTACH_REASON_LAUNCH  
Připojte, protože proces byl spuštěn.

ATTACH_REASON_USER  
Připojení z důvodu požadavku uživatele.

## <a name="remarks"></a>Poznámky
Tyto hodnoty jsou použity jako parametr [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) a [připojit](../../../extensibility/debugger/reference/idebugprogramex2-attach.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)  
[Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)
