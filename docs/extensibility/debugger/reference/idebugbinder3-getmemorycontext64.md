---
title: IDebugBinder3::GetMemoryContext64 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetMemoryContext64
- IDebugBinder3::GetMemoryContext64
ms.assetid: f021fd16-9fc7-4c41-86af-e54e6224cfbb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 522d6cc0888f3ccbfd8c39a9ec313f7e06add25f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877471"
---
# <a name="idebugbinder3getmemorycontext64"></a>IDebugBinder3::GetMemoryContext64
Převede objekt umístění nebo adresu paměti 64-bit na místní paměti.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetMemoryContext64 (
    IDebugField*           pField,
    UINT64                 uConstant,
    IDebugMemoryContext2** ppMemCxt
);
```

```csharp
int GetMemoryContext64 (
    IDebugField              pField,
    ulong                    uConstant,
    out IDebugMemoryContext2 ppMemCxt
);
```

#### <a name="parameters"></a>Parametry
`pField`

 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) , který popisuje objekt, který má být vyhledán. Pokud `NULL`, pak použijte `dwConstant` místo.

`uConstant`

 [in] Adresa paměti 64-bit, jako je například 0x50000000.

`ppMemCxt`

 [out] Vrátí [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) rozhraní, které představuje adresu objektu, nebo adresy v paměti.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="example"></a>Příklad
Následující příklady vytvoří objekt, který implementuje [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md) rozhraní a tato metoda používá k načtení kontextu paměti.

```cpp
HRESULT CValueProperty::GetMemoryContext ( IDebugMemoryContext2** out_ppMemoryContext )
{
    // precondition
    REQUIRE( NULL != out_ppMemoryContext );

    if (NULL == out_ppMemoryContext)
        return E_POINTER;

    *out_ppMemoryContext = NULL;

    INVARIANT( this );

    if (!this->ClassInvariant())
        return E_UNEXPECTED;

    if (VT_EMPTY == this->m_VarValue.vt)
    {
        return E_FAIL;
    }

    // function body
    if (NULL != this->m_pBinder)
    {
        UINT64 dwOffset = 0;

        DEBUG_PROPERTY_INFO dpInfo;
        HRESULT HR = this->GetPropertyInfo(DEBUGPROP_INFO_VALUE,
                                           10, // RADIX
                                           DEFAULT_TIMEOUT,
                                           NULL,
                                           0,
                                           &dpInfo);
        if (ENSURE( S_OK == HR ))
        {
            REQUIRE( NULL != dpInfo.bstrValue );
            REQUIRE( NULL == dpInfo.bstrName );
            REQUIRE( NULL == dpInfo.bstrFullName );
            REQUIRE( NULL == dpInfo.bstrType );
            REQUIRE( NULL == dpInfo.pProperty );

            wchar_t * end;
            dwOffset = _wcstoui64(dpInfo.bstrValue, &end, 0); // base 0 to allow 0x if it's ever output
            ::SysFreeString(dpInfo.bstrValue);
        }

        if (CComQIPtr<IDebugBinder3> binder3 = this->m_pBinder)
            HR = binder3->GetMemoryContext64(NULL, dwOffset, out_ppMemoryContext);
        else
            HR = this->m_pBinder->GetMemoryContext(NULL, (DWORD)(__int32)dwOffset, out_ppMemoryContext);

        if (ENSURE( S_OK == HR ))
        {
            REQUIRE( NULL != *out_ppMemoryContext );
        }
    }

    // postcondition
    INVARIANT( this );

    HRESULT HR = E_FAIL;

    if (NULL != *out_ppMemoryContext)
    {
        HR = S_OK;
    }

    return HR;
}
```

## <a name="see-also"></a>Viz také
- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
