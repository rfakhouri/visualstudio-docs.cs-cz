---
title: IDebugComPlusSymbolProvider::UpdateSymbols | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- UpdateSymbols
- IDebugComPlusSymbolProvider::UpdateSymbols
ms.assetid: d530f6f1-4af2-454b-bab0-02478a8fe81e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c6c3c396dbea0e005012162080590a0b84ec9f5b
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "56413290"
---
# <a name="idebugcomplussymbolproviderupdatesymbols"></a>IDebugComPlusSymbolProvider::UpdateSymbols
Aktualizuje symboly ladění do paměti ze zadaného datového proudu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT UpdateSymbols (
    ULONG32  ulAppDomainID,
    GUID     guidModule,
    IStream* pUpdateStream
);
```

```csharp
int UpdateSymbols (
    uint    ulAppDomainID,
    Guid    guidModule,
    IStream pUpdateStream
);
```

#### <a name="parameters"></a>Parametry
`ulAppDomainID`  
[in] Identifikátor domény aplikace.

`guidModule`  
[in] Jedinečný identifikátor modulu.

`pUpdateStream`  
[in] Datový proud, který obsahuje symboly ladění aktualizované.

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak pro tuto metodu implementovat **CDebugSymbolProvider** objekt, který zveřejňuje [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) rozhraní.

```cpp
HRESULT CDebugSymbolProvider::UpdateSymbols(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    IStream* pUpdateStream
)
{
    ASSERT(!"Use UpdateSymbols2 on IDebugENCSymbolProvider2");
    return E_NOTIMPL;
}

HRESULT CDebugSymbolProvider::UpdateSymbols2(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    IStream* pUpdateStream,
    LINEDELTA* pDeltaLines,
    ULONG cDeltaLines
)
{
    HRESULT hr = S_OK;
    CComPtr<CModule> pModule;
    Module_ID idModule(ulAppDomainID, guidModule);

    METHOD_ENTRY( CDebugSymbolProvider::UpdateSymbols );

    IfFailGo( GetModule( idModule, &pModule ) );
    IfFailGo( pModule->UpdateSymbols( pUpdateStream, pDeltaLines, cDeltaLines ) );

Error:

    METHOD_EXIT( CDebugSymbolProvider::UpdateSymbols, hr );

    return hr;
}
```

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
