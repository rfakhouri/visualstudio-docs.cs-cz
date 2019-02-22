---
title: THREADSTATE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- THREADSTATE
helpviewer_keywords:
- THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 96eb95d39c60952c48e62c0e2e61edefeaa59783
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694371"
---
# <a name="threadstate"></a>THREADSTATE
Určuje stav vlákna.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_THREADSTATE { 
   THREADSTATE_RUNNING = 0x0001,
   THREADSTATE_STOPPED = 0x0002,
   THREADSTATE_FRESH   = 0x0003,
   THREADSTATE_DEAD    = 0x0004,
   THREADSTATE_FROZEN  = 0x0005
};
typedef DWORD THREADSTATE;
```

```csharp
public enum enum_THREADSTATE { 
   THREADSTATE_RUNNING = 0x0001,
   THREADSTATE_STOPPED = 0x0002,
   THREADSTATE_FRESH   = 0x0003,
   THREADSTATE_DEAD    = 0x0004,
   THREADSTATE_FROZEN  = 0x0005
};
```

## <a name="members"></a>Členové
 THREADSTATE_RUNNING znamená, že je spuštěn podproces.

 THREADSTATE_STOPPED označuje, že vlákno zastavena kvůli zarážku.

 THREADSTATE_FRESH označuje, že se vytvořila vlákno, ale ještě není spuštěno kódu.

 THREADSTATE_DEAD označuje, že vlákno je neaktivní.

 THREADSTATE_FROZEN označuje, že je zmrazené vlákno (bez spuštění lze provést).

## <a name="remarks"></a>Poznámky
 Používá pro `dwThreadState` pole [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) struktury.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)