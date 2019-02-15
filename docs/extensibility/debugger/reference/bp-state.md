---
title: BP_STATE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_STATE
helpviewer_keywords:
- BP_STATE enumeration
ms.assetid: 08aa6a3f-3e5f-4c83-8eca-7b7b5f8e208d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 95e228a3aa0e96eedcf0413df7680e7a5664b707
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315414"
---
# <a name="bpstate"></a>BP_STATE
Určuje existenci vázaná zarážka a také určuje, jestli je povolené.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
typedef DWORD BP_STATE;
```

```csharp
public enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
```

## <a name="members"></a>Členové
BPS_NONE  
Určuje, že neexistuje žádná zarážka.

BPS_DELETED  
Určuje, že zarážka byla odstraněna.

BPS_DISABLED  
Určuje, že je zakázaná zarážka.

BPS_ENABLED  
Určuje, zda je povolena zarážka.

## <a name="remarks"></a>Poznámky
Vrátilo [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)
