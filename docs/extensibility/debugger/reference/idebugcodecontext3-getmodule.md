---
title: IDebugCodeContext3::GetModule | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCodeContext3::GetModule
ms.assetid: 8e4317b8-8255-486c-a896-a68ed94f8aa1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ae925ab4c05db45d09638070df9291541f19a869
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703718"
---
# <a name="idebugcodecontext3getmodule"></a>IDebugCodeContext3::GetModule
Získá odkaz na rozhraní modulu ladění.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetModule(
    IDebugModule2 **ppModule
);
```

```csharp
public int GetModule(
    out IDebugModule2 ppModule
);
```

#### <a name="parameters"></a>Parametry
`ppModule`

 [out] Odkaz na ladicí rozhraní modulu.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak pro tuto metodu implementovat **CDebugCodeContext** objekt, který zveřejňuje [IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md) rozhraní.

```cpp
HRESULT CDebugCodeContext::GetModule(IDebugModule2** ppModule)
{
    HRESULT hr = S_OK;
    CComPtr<CModule> pModule;

    IfFalseGo( ppModule, E_INVALIDARG );
    *ppModule = NULL;

    IfFailGo( this->GetModule(&pModule) );
    IfFailGo( pModule->QueryInterface(IID_IDebugModule2, (void**) ppModule) );

Error:

    return hr;
}
```

## <a name="see-also"></a>Viz také
- [IDebugCodeContext3](../../../extensibility/debugger/reference/idebugcodecontext3.md)
