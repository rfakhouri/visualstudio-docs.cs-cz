---
title: IDebugCustomAttributeQuery::IsCustomAttributeDefined | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCustomAttributeQuery::IsCustomAttributeDefined
- IsCustomAttributeDefined
ms.assetid: c7425db6-4347-4f69-8f88-337ddaa34fa6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8a907d6460a9bf31e501ed4c2239cb31112a39f5
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708222"
---
# <a name="idebugcustomattributequeryiscustomattributedefined"></a>IDebugCustomAttributeQuery::IsCustomAttributeDefined
Určuje, zda je definována zadaného vlastního atributu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT IsCustomAttributeDefined(
    LPCOLESTR pszCustomAttributeName
);
```

```csharp
int IsCustomAttributeDefined(
    string pszCustomAttributeName
);
```

#### <a name="parameters"></a>Parametry
`pszCustomAttributeName`

 [in] Název vlastního atributu.

## <a name="return-value"></a>Návratová hodnota
Pokud je definován vlastní atribut, vrátí `S_OK`; v opačném případě vrátí `S_FALSE`.

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak pro tuto metodu implementovat **CDebugClassFieldSymbol** objekt, který zveřejňuje [IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md) rozhraní.

```cpp
HRESULT CDebugClassFieldSymbol::IsCustomAttributeDefined(
    LPCOLESTR pszCustomAttribute
)
{
    HRESULT hr = S_FALSE;
    CComPtr<IMetaDataImport> pMetadata;
    mdToken token = mdTokenNil;
    CComPtr<IDebugField> pField;
    CComPtr<IDebugCustomAttributeQuery> pCA;

    ASSERT(IsValidWideStringPtr(pszCustomAttribute));

    METHOD_ENTRY( CDebugClassFieldSymbol::IsCustomAttributeDefined );

    IfFalseGo( pszCustomAttribute, E_INVALIDARG );

    IfFailGo( m_spSH->GetMetadata( m_spAddress->GetModule(), &pMetadata ) );

    IfFailGo( CDebugCustomAttribute::GetTokenFromAddress( m_spAddress, &token) );
    IfFailGo( pMetadata->GetCustomAttributeByName( token,
              pszCustomAttribute,
              NULL,
              NULL ) );
Error:

    METHOD_EXIT( CDebugClassFieldSymbol::IsCustomAttributeDefined, hr );

    if (hr != S_OK)
    {
        hr = S_FALSE;
    }

    return hr;
}
```

## <a name="see-also"></a>Viz také
- [IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)
