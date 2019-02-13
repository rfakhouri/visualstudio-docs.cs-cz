---
title: IDiaSession::symbolById | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 71072c597a445d54fc3429e949b24fde81761fc1
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227667"
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
Načte symbol podle jejího jedinečného identifikátoru.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT symbolById (
    DWORD        id,
    IDiaSymbol** ppSymbol
);
```

#### <a name="parameters"></a>Parametry
`id`  
[in] Jedinečný identifikátor.

`ppSymbol`  
[out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) načíst objekt představující symbol.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
Zadaný identifikátor je jedinečná hodnota používaná interně pomocí sady DIA SDK jedinečných aby všechny symboly.

Tuto metodu lze použít například k načtení symbol představující typ jiného symbolu (podívejte se na příklad).

## <a name="example"></a>Příklad
Tento příklad načte [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) představující typ jiného symbolu. Tento příklad ukazuje způsob použití `symbolById` metoda v relaci. Je jednodušší přístup k volání [idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md) metody k získání typu symbol přímo.

```C++
IDiaSymbol *GetSymbolType(IDiaSymbol *pSymbol, IDiaSession *pSession)
{
    IDiaSymbol *pTypeSymbol = NULL;
    if (pSymbol != NULL && pSession != NULL)
    {
        DWORD symbolTypeId;
        pSymbol->get_typeId(&symbolTypeId);
        pSession->symbolById(symbolTypeId, &pTypeSymbol);
    }
    return(pTypeSymbol);
}
```

## <a name="see-also"></a>Viz také
[IDiaSession](../../debugger/debug-interface-access/idiasession.md)  
[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)  
[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)
