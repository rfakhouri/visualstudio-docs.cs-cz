---
title: THREADPROPERTIES | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- THREADPROPERTIES
helpviewer_keywords:
- THREADPROPERTIES structure
ms.assetid: 7d397207-db03-4ec0-9f79-3794056ed89f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 55b3334c8bd28d3975f06aa39ca8c7fd719f1f9e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694475"
---
# <a name="threadproperties"></a>THREADPROPERTIES
Popisuje vlastnosti vlákno.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagTHREADPROPERTIES { 
   THREADPROPERTY_FIELDS dwFields;
   DWORD                 dwThreadId;
   DWORD                 dwSuspendCount;
   DWORD                 dwThreadState;
   BSTR                  bstrPriority;
   BSTR                  bstrName;
   BSTR                  bstrLocation;
} THREADPROPERTIES;
```

```csharp
public struct THREADPROPERTIES { 
   public uint   dwFields;
   public uint   dwThreadId;
   public uint   dwSuspendCount;
   public uint   dwThreadState;
   public string bstrPriority;
   public string bstrName;
   public string bstrLocation;
};
```

## <a name="members"></a>Členové
 dwFields A kombinace příznaků z [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md) výčet popisující, která pole v této struktuře jsou platné.

 dwThreadId ID vlákna.

 dwSuspendCount vlákno pozastavit count.

 dwThreadState A maximum [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md) výčet označující stav provozní vlákna.

 řetězec určující priorita vlákna; bstrPriority například "Vyšší než normální", "Normal" nebo "Kritický čas".

 bstName název vlákna.

 bstrLocation umístění podprocesu (obvykle nejvyššího rámec zásobníku), obvykle vyjádřený jako název metody, kde aktuálně zastavení spuštění.

## <a name="remarks"></a>Poznámky
 Tato struktura je vyplněna voláním [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) metody. Takže vrácené informace se obvykle používá při naplňování **vlákna** okna.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)
- [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)
- [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md)