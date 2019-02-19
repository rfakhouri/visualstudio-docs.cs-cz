---
title: IDebugComPlusSymbolProvider::GetArrayTypeFromAddress | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetArrayTypeFromAddress
- IDebugComPlusSymbolProvider::GetArrayTypeFromAddress
ms.assetid: cc0c53f1-8c0f-49fa-8dbe-bc155e9ce0ef
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0878f4224d024e353c2c7ab798450a65e9677178
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "56413342"
---
# <a name="idebugcomplussymbolprovidergetarraytypefromaddress"></a>IDebugComPlusSymbolProvider::GetArrayTypeFromAddress
Načte zadejte informace o zadané pole na základě daných jeho adresa pro ladění.

## <a name="syntax"></a>Syntaxe

```
[C++]
HRESULT GetArrayTypeFromAddress(
    IDebugAddress* pAddress,
    BYTE*          pSig,
    DWORD          dwSigLength,
    IDebugField**  ppField
);
```

```
[C#]
int GetArrayTypeFromAddress(
    IDebugAddress   pAddress,
    int[]           pSig,
    uint            dwSigLength,
    out IDebugField ppField
);
```

#### <a name="parameters"></a>Parametry
`pAddress`  
[in] Adresa pro ladění reprezentována [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.

`pSig`  
[in] Pole, které chcete prozkoumat.

`dwSigLength`  
[in] Délka v bajtech `pSig` pole.

`ppField`  
[out] Vrátí typ pole reprezentovaná [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) rozhraní.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak pro tuto metodu implementovat **CDebugSymbolProvider** objekt, který zveřejňuje [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) rozhraní.

```cpp
HRESULT CDebugSymbolProvider::GetArrayTypeFromAddress(
    IDebugAddress *pAddress,
    BYTE *pSig,
    DWORD dwSigLength,
    IDebugField **ppField)
{
    HRESULT hr = E_FAIL;
    CDEBUG_ADDRESS da;
    CDebugGenericParamScope* pGenScope = NULL;

    METHOD_ENTRY( CDebugDynamicFieldSymbol::GetArrayTypeFromAddress );

    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));
    ASSERT(IsValidWritePtr(ppField, IDebugField*));

    IfFailGo( pAddress->GetAddress(&da) );

    if ( S_OK == hr )
    {
        IfNullGo( pGenScope = new CDebugGenericParamScope(da.GetModule(), da.tokClass, da.GetMethod()), E_OUTOFMEMORY );

        IfFailGo( this->CreateType((const COR_SIGNATURE*)(pSig), dwSigLength, da.GetModule(), mdMethodDefNil, pGenScope, ppField) );
    }

Error:

    METHOD_EXIT( CDebugDynamicFieldSymbol::GetArrayTypeFromAddress, hr );
    RELEASE( pGenScope );
    return hr;
}
```

## <a name="see-also"></a>Viz také
[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
