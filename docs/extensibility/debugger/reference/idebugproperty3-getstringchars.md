---
title: IDebugProperty3::GetStringChars | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty3::GetStringChars
helpviewer_keywords:
- IDebugProperty3::GetStringChars
ms.assetid: 832c37f3-85cb-4227-8ab2-f27a80eafe90
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b087997fab72e71abf4380df6d5c03910d1a57eb
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212258"
---
# <a name="idebugproperty3getstringchars"></a>IDebugProperty3::GetStringChars
Načte řetězec přidružený k této vlastnosti a ukládá ho do uživatelem zadané vyrovnávací paměti.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetStringChars(
    ULONG  buflen,
    WCHAR* rgString,
    ULONG* pceltFetched
);
```

```csharp
int GetStringChars(
    uint       buflen,
    out string rgString,
    out uint   pceltFetched
);
```

## <a name="parameters"></a>Parametry
`buflen`\
[in] Maximální počet znaků, které může obsahovat uživatelem zadané vyrovnávací paměti.

`rgString`\
[out] Vrátí řetězec.

 [C++ pouze], `rgString` je ukazatel do vyrovnávací paměti, která přijímá znaků Unicode řetězce. Tuto vyrovnávací paměť musí být dlouhý aspoň `buflen` znaků (ne v bajtech) velikosti.

`pceltFetched`\
[out] Pokud se vrátí počet znaků ve skutečnosti uloženy ve vyrovnávací paměti. (Může být `NULL` v jazyce C++.)

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
V jazyce C++, musí věnovat pozornost – pomáhat zajistit, že vyrovnávací paměť je alespoň `buflen` znaků Unicode. Všimněte si, že znak Unicode je 2 bajty dlouhý.

> [!NOTE]
> Vrácený řetězec v jazyce C++, nezahrnuje ukončující znak null. Pokud tento parametr zadaný, `pceltFetched` určí počet znaků v řetězci.

## <a name="example"></a>Příklad

```cpp
CStringW RetrievePropertyString(IDebugProperty2 *pPropInfo)
{
    CStringW returnString = L"";
    CComQIPtr<IDebugProperty3> pProp3 = pPropInfo->pProperty;
    If (pProp3 != NULL) {
        ULONG dwStrLen = 0;
        HRESULT hr;
        hr = pProp3->GetStringCharLength(&dwStrLen);
        if (SUCCEEDED(hr) && dwStrLen > 0) {
            ULONG dwRead;
            CStrBufW buf(returnString,dwStrLen,CStrBuf::SET_LENGTH);
            hr = pProp3->GetStringChars(dwStrLen,
                                        reinterpret_cast<WCHAR*>(static_cast<CStringW::PXSTR>(buf)),
                                        &dwRead);
        }
    }
    return(returnString);
}
```

## <a name="see-also"></a>Viz také:
- [GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
