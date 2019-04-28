---
title: Idiaenumsymbolsbyaddr – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbolsbyAddr interface
ms.assetid: 37d3dcdf-e4fa-4354-b5e1-8843566b52ac
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 96ed66156fae24e22c549fffb6eb982a45e7e3f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62830367"
---
# <a name="idiaenumsymbolsbyaddr"></a>IDiaEnumSymbolsByAddr
Vytvoří výčet podle adresy různé symboly obsažené ve zdroji dat.

## <a name="syntax"></a>Syntaxe

```
IDiaEnumSymbolsByAddr : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaEnumSymbolsByAddr`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaEnumSymbolsByAddr::symbolByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyaddr.md)|Pozice výčtu pomocí provádí vyhledávání podle oddílu a posun.|
|[IDiaEnumSymbolsByAddr::symbolByRVA](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyrva.md)|Pozice výčtu pomocí provádí vyhledávání podle relativní virtuální adresu (RVA).|
|[IDiaEnumSymbolsByAddr::symbolByVA](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)|Pozice výčtu pomocí provádí vyhledávání podle virtuální adresy (VA).|
|[IDiaEnumSymbolsByAddr::Next](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-next.md)|Načte další symboly v pořadí podle adresy. Aktualizuje pozice čítače výčtu počet načtených prvků.|
|[IDiaEnumSymbolsByAddr::Prev](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-prev.md)|Načte předchozí symboly v pořadí podle adresy. Aktualizuje pozice čítače výčtu počet načtených prvků.|
|[IDiaEnumSymbolsByAddr::Clone](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-clone.md)|Vytvoří kopii tohoto objektu.|

## <a name="remarks"></a>Poznámky
Toto rozhraní poskytuje symboly seskupené podle adres. Pro práci se symboly seskupené podle typu, třeba `SymTagUDT` (uživatelem definovaný typ) nebo `SymTagBaseClass`, použijte [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
Získat voláním toto rozhraní [idiasession::getsymbolsbyaddr –](../../debugger/debug-interface-access/idiasession-getsymbolsbyaddr.md) metody.

## <a name="example"></a>Příklad
Tato funkce zobrazí název a adresu všechny symboly seřazené podle relativní virtuální adresu.

```C++
void ShowSymbolsByAddress(IDiaSession *pSession)
{
    CComPtr<IDiaEnumSymbolsByAddr> pEnumByAddr;
    if ( FAILED( psession->getSymbolsByAddr( &pEnumByAddr ) ) )
    {
        Fatal( "getSymbolsByAddr" );
    }
    CComPtr<IDiaSymbol> pSym;
    if ( FAILED( pEnumByAddr->symbolByAddr( 1, 0, &pSym ) ) )
    {
        Fatal( "symbolByAddr" );
    }
    DWORD rvaLast = 0;
    if ( pSym->get_relativeVirtualAddress( &rvaLast ) == S_OK )
    {
        pSym = 0;
        if ( FAILED( pEnumByAddr->symbolByRVA( rvaLast, &pSym ) ) )
        {
            Fatal( "symbolByAddr" );
        }
        printf( "Symbols in order\n" );
        do
        {
            CDiaBSTR name;
            if ( pSym->get_name( &name ) != S_OK )
            {
                printf( "\t0x%08X (%ws) <no name>\n", rvaLast );
            }
            else
            {
                printf( "\t0x%08X %ws\n", rvaLast, name );
            }
            pSym = 0;
            celt = 0;
            if ( FAILED( hr = pEnumByAddr->Next( 1, &pSym, &celt ) ) )
            {
                break;
            }
        } while ( celt == 1 );
    }
}
```

## <a name="requirements"></a>Požadavky
Záhlaví: Dia2.h

Knihovna: diaguids.lib

DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaSession::getSymbolsByAddr](../../debugger/debug-interface-access/idiasession-getsymbolsbyaddr.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
