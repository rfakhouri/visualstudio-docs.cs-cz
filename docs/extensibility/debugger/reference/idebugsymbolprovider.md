---
title: IDebugSymbolProvider | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider
helpviewer_keywords:
- IDebugSymbolProvider interface
ms.assetid: df5f095f-1dee-46f9-84cf-92417c71d5fb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6275cc68ac7bd9948416046f851e778ee51a83dd
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347471"
---
# <a name="idebugsymbolprovider"></a>IDebugSymbolProvider
Toto rozhraní představuje poskytovatele symbol, který obsahuje symboly a typy, vrací jako pole.

## <a name="syntax"></a>Syntaxe

```
IDebugSymbolProvider : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
Poskytovatel symbolů musí implementovat toto rozhraní k poskytnutí symbolů a zadejte informace, které vyhodnocovače výrazů.

## <a name="notes-for-callers"></a>Poznámky pro volající
Toto rozhraní je získat pomocí modelu COM `CoCreateInstance` – funkce (pro poskytovatele nespravované symbol) nebo načtením odpovídající spravovaný kód sestavení a vytvoření instance zprostředkovatele symbol na základě informací v tomto sestavení. Ladicí stroj vytvoří poskytovatel symbolů pro práci v koordinaci se chyba při vyhodnocování výrazu. Podívejte se na příklad pro jeden ze způsobů vytvoření instance tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDebugSymbolProvider`.

|Metoda|Popis|
|------------|-----------------|
|`Initialize`|Zastaralé Nepoužívejte.|
|`Uninitialize`|Zastaralé Nepoužívejte.|
|[GetContainerField](../../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md)|Získá pole s údajem o adresa pro ladění.|
|`GetField`|Zastaralé Nepoužívejte.|
|[GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)|Mapuje umístění dokumentu do pole adresy ladění.|
|[GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)|Mapuje kontext dokumentu do pole adresy ladění.|
|[GetContextFromAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getcontextfromaddress.md)|Mapuje adresu ladění do kontextu dokumentu.|
|[GetLanguage](../../../extensibility/debugger/reference/idebugsymbolprovider-getlanguage.md)|Získá jazyk používaný ke kompilaci kódu na adrese ladění.|
|`GetGlobalContainer`|Zastaralé Nepoužívejte.|
|[GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)|Získá pole představující metodu plně kvalifikovaný název.|
|[GetClassTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getclasstypebyname.md)|Získá typ pole třídy představující plně kvalifikovaný název třídy.|
|[GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)|Vytvoří čítač pro obory názvů, které jsou přidružené k adresám ladění.|
|[GetTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-gettypebyname.md)|Název symbolu se mapuje na typ symbolu.|
|[GetNextAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnextaddress.md)|Získá adresu ladění, který následuje adresa pro danou ladění v metodě.|

## <a name="remarks"></a>Poznámky
Toto rozhraní mapuje umístění dokumentu do adresy ladění a naopak.

## <a name="requirements"></a>Požadavky
Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="example"></a>Příklad
Tento příklad ukazuje, jak vytvořit instanci zprostředkovatele symbol uveden její identifikátor GUID (ladicí stroj musí vědět, tato hodnota).

```cpp
// A debug engine uses its own symbol provider and would know the GUID
// of that provider.
IDebugSymbolProvider *GetSymbolProvider(GUID *pSymbolProviderGuid)
{
    // This is typically defined globally. For this example, it is
    // defined here.
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";
    IDebugSymbolProvider *pProvider = NULL;
    if (pSymbolProviderGuid != NULL) {
        CLSID clsidProvider = { 0 };
        ::GetSPMetric(*pSymbolProviderGuid,
                      storetypeFile,
                      metricCLSID,
                      &clsidProvider,
                      strRegistrationRoot);
        if (IsEqualGUID(clsidProvider,GUID_NULL)) {
            // No file type provider, try metadata provider.
            ::GetSPMetric(*pSymbolProviderGuid,
                          ::storetypeMetadata,
                          metricCLSID,
                          &clsidProvider,
                          strRegistrationRoot);
        }
        if (!IsEqualGUID(clsidProvider,GUID_NULL)) {
            CComPtr<IDebugSymbolProvider> spSymbolProvider;
            spSymbolProvider.CoCreateInstance(clsidProvider);
            if (spSymbolProvider != NULL) {
                pProvider = spSymbolProvider.Detach();
            }
        }
    }
    return(pProvider);
}
```

## <a name="see-also"></a>Viz také:
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
