---
title: IDebugSymbolProvider | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider
helpviewer_keywords:
- IDebugSymbolProvider interface
ms.assetid: df5f095f-1dee-46f9-84cf-92417c71d5fb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: db4e5592fac73f629aba69fa23d1a7163c794875
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62915798"
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

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
