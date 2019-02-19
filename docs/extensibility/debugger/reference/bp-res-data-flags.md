---
title: BP_RES_DATA_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_RES_DATA_FLAGS
helpviewer_keywords:
- BP_RES_DATA_FLAGS enumeration
ms.assetid: d97611e2-def6-45a9-ad7d-eedf2ad4c82b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b111e98edb1d364a466157a6db4c0089617f18de
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "56413017"
---
# <a name="bpresdataflags"></a>BP_RES_DATA_FLAGS
Určuje, zda je datová zarážka emulovaných nebo implementované v hardwaru.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BP_RES_DATA_FLAGS {
    BP_RES_DATA_EMULATED = 0x0001
};
typedef DWORD BP_RES_DATA_FLAGS;
```

```csharp
public enum enum_BP_RES_DATA_FLAGS {
    BP_RES_DATA_EMULATED = 0x0001
};
```

## <a name="members"></a>Členové
BP_RES_DATA_EMULATED  
Určuje, že je emulovaných datová zarážka.

## <a name="remarks"></a>Poznámky
Používá pro `dwFlags` člena [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) struktury.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)
