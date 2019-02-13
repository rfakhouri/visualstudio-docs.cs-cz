---
title: Idiasymbol::get_basetype – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_baseType method
ms.assetid: 5c69a241-a8d3-48ed-8b36-27463a196572
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c2844003bf7ec81b256537fe06520dfdff473faa
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227274"
---
# <a name="idiasymbolgetbasetype"></a>IDiaSymbol::get_baseType
Získá základní typ pro tento symbol<em>.</em>

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_baseType (
    DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parametry
`pRetVal`  
[out] Vrátí hodnotu z [basictype – výčet](../../debugger/debug-interface-access/basictype.md) výčet určující základní typ symbolu.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
Prvním načtení typ symbolu a pak dotazem, který vrátil typ pro základní typ stanovit základní typ pro symbol. Všimněte si, že některé symboly nemusí mít základní typ. – například název struktury.

## <a name="example"></a>Příklad

```C++
IDiaSymbol* pType;
CComPtr<IDiaSymbol> pBaseType;
if (pType->get_type( &pBaseType ) == S_OK)
{
    BasicType btBaseType;
    if (pBaseType->get_baseType((DWORD *)&btBaseType) == S_OK)
    {
        // Do something with basic type.
    }
}
```

## <a name="requirements"></a>Požadavky

|Požadavek|Popis|
|-----------------|-----------------|
|Záhlaví:|dia2.h|
|Verze:|V7.0 DIA SDK|

## <a name="see-also"></a>Viz také
[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)  
[BasicType – výčet](../../debugger/debug-interface-access/basictype.md)  
[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)
