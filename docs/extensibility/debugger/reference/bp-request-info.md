---
title: BP_REQUEST_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_REQUEST_INFO
helpviewer_keywords:
- BP_REQUEST_INFO structure
ms.assetid: 42a31412-5b6b-47fe-a762-0c2bc769e1cc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 54af482e8896ce1905700312e59bd156c40b556d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62889006"
---
# <a name="bprequestinfo"></a>BP_REQUEST_INFO
Obsahuje informace potřebné k implementaci zarážku.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _BP_REQUEST_INFO {
    BPREQI_FIELDS   dwFields;
    GUID            guidLanguage;
    BP_LOCATION     bpLocation;
    IDebugProgram2* pProgram;
    BSTR            bstrProgramName;
    IDebugThread2*  pThread;
    BSTR            bstrThreadName;
    BP_CONDITION    bpCondition;
    BP_PASSCOUNT    bpPassCount;
    BP_FLAGS        dwFlags;
} BP_REQUEST_INFO;
```

```csharp
public struct BP_REQUEST_INFO {
    public uint           dwFields;
    public Guid           guidLanguage;
    public BP_LOCATION    bpLocation;
    public IDebugProgram2 pProgram;
    public string         bstrProgramName;
    public IDebugThread2  pThread;
    public string         bstrThreadName;
    public BP_CONDITION   bpCondition;
    public BP_PASSCOUNT   bpPassCount;
    public uint           dwFlags;
};
```

## <a name="members"></a>Členové
`dwFields` Kombinace příznaků z [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) výčet, který určuje, která pole jsou vyplněna.

`guidLanguage` Identifikátor GUID jazyka.

`bpLocation` [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktura, která určuje typ umístění zarážky.

`pProgram` [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který reprezentuje aplikaci, ve kterém dochází k zarážce.

`bstrProgramName` Název aplikace, ve kterém dochází k zarážce.

`pThread` [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vláken, ve kterém dochází k zarážce.

`bstrThreadName` Název vlákna, ve kterém dochází k zarážce.

`bpCondition` [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) struktura, která popisuje podmínky, za kterých se zarážka aktivuje.

`bpPassCount` [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) strukturu, která obsahuje informace o počtu průchodu této zarážky.

`dwFlags` Kombinace příznaků z [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) výčet, který určuje příznaky pro požadované zarážky.

## <a name="remarks"></a>Poznámky
Tato struktura je vrácený [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) metody.

Pokud potřebujete získat ladicí stroj dodavatele identifikátor GUID, omezení zarážky nebo zarážky s trasováním, přečtěte si [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)
- [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)
- [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
- [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)
- [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
