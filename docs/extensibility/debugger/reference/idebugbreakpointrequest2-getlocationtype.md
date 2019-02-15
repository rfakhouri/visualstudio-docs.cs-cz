---
title: IDebugBreakpointRequest2::GetLocationType | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBreakpointRequest2::GetLocationType
helpviewer_keywords:
- IDebugBreakpointRequest2::GetLocationType
ms.assetid: b6d14c59-d3aa-48ff-8278-f6b5bba9c2f3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: afddb4f27eaae9ae9960ae07127d88d0d4588d1f
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315674"
---
# <a name="idebugbreakpointrequest2getlocationtype"></a>IDebugBreakpointRequest2::GetLocationType
Získá typ umístění zarážky tohoto požadavku na zarážku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetLocationType(
    BP_LOCATION_TYPE* pBPLocationType
);
```

```csharp
int GetLocationType(
    out enum_BP_LOCATION_TYPE pBPLocationType
);
```

#### <a name="parameters"></a>Parametry
`pBPLocationType` [out] Vrátí hodnotu z [BP_LOCATION_TYPE](../../../extensibility/debugger/reference/bp-location-type.md) výčet, který popisuje umístění této žádosti zarážku.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_FAIL` Pokud `bpLocation` pole v přidruženém [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) struktura není platná.

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CDebugBreakpointRequest` objekt, který zveřejňuje[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) rozhraní.

```
HRESULT CDebugBreakpointRequest::GetLocationType(BP_LOCATION_TYPE* pBPLocationType)
{
    HRESULT hr;

    if (pBPLocationType)
    {
        // Set default BP_LOCATION_TYPE.
        *pBPLocationType = BPLT_NONE;

        // Check if the BPREQI_BPLOCATION flag is set in BPREQI_FIELDS.
        if (IsFlagSet(m_bpRequestInfo.dwFields, BPREQI_BPLOCATION))
        {
            // Get the new BP_LOCATION_TYPE.
            *pBPLocationType = m_bpRequestInfo.bpLocation.bpLocationType;
            hr = S_OK;
        }
        else
        {
            hr = E_FAIL;
        }
    }
    else
    {
        hr = E_INVALIDARG;
    }

    return hr;
}
```

## <a name="see-also"></a>Viz také
[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)  
[BP_LOCATION_TYPE](../../../extensibility/debugger/reference/bp-location-type.md)  
[BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)  
[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
