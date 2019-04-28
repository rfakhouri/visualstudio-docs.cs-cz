---
title: Idiaenumlinenumbers – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers interface
ms.assetid: cdf07b4f-19e4-4dcd-8af8-c2dbca586a7c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 49257aa3b9b51a1e8b62c867ced030b853deae9c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62833505"
---
# <a name="idiaenumlinenumbers"></a>IDiaEnumLineNumbers
Provede výčet různých čísla řádků, které jsou obsaženy ve zdroji dat.

## <a name="syntax"></a>Syntaxe

```
IDiaEnumLineNumbers : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaEnumLineNumbers`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaEnumLineNumbers::get__NewEnum](../../debugger/debug-interface-access/idiaenumlinenumbers-get-newenum.md)|Načte [rozhraní IEnumVARIANT](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ienumvariant) verzi výčet.|
|[IDiaEnumLineNumbers::get_Count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md)|Získá počet čísel řádků.|
|[IDiaEnumLineNumbers::Item](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md)|Získá číslo řádku pomocí indexu.|
|[IDiaEnumLineNumbers::Next](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md)|Načte zadaný počet čísel řádků v pořadí výčtu.|
|[IDiaEnumLineNumbers::Skip](../../debugger/debug-interface-access/idiaenumlinenumbers-skip.md)|Vynechá zadaný počet čísel řádků v sekvenci výčtu.|
|[IDiaEnumLineNumbers::Reset](../../debugger/debug-interface-access/idiaenumlinenumbers-reset.md)|Návrat na začátek sekvence výčtu.|
|[IDiaEnumLineNumbers::Clone](../../debugger/debug-interface-access/idiaenumlinenumbers-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|

## <a name="remarks"></a>Poznámky

## <a name="notes-for-callers"></a>Poznámky pro volající
Toto rozhraní je získán voláním jedné z následujících metod v [idiasession –](../../debugger/debug-interface-access/idiasession.md) rozhraní:

- [IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md)

- [IDiaSession::findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)

- [IDiaSession::findLinesByRVA](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)

- [IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)

- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)

## <a name="example"></a>Příklad
Tento příklad ukazuje, jak získat `IDiaEnumLineNumbers` rozhraní v relaci. V takovém případě tento příklad ukazuje, jak získat výčet číslo řádku funkce (představované `pSymbol`). Úplný příklad použití čísla řádků, najdete v článku [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) rozhraní.

```C++
void dumpFunctionLines( IDiaSymbol* pSymbol, IDiaSession* pSession )
{
    ULONGLONG length = 0;
    DWORD isect = 0;
    DWORD offset = 0;
    pSymbol->get_addressSection( &isect );
    pSymbol->get_addressOffset( &offset );
    pSymbol->get_length( &length );
    if ( isect != 0 && length > 0 )
    {
        CComPtr< IDiaEnumLineNumbers > pLines;
        if ( SUCCEEDED( pSession->findLinesByAddr(
                                      isect,
                                      offset,
                                      static_cast<DWORD>( length ),
                                      &pLines )
                      )
           )
        {
            // Do something with the enumeration
        }
    }
}
```

## <a name="requirements"></a>Požadavky
Záhlaví: Dia2.h

Knihovna: diaguids.lib

DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)
- [IDiaSession::findLinesByRVA](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)
- [IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)
- [IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md)
- [IDiaSession::findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)
