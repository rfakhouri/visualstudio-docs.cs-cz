---
title: Idiasectioncontrib – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib interface
ms.assetid: 371d40f6-ca0e-4d7e-9210-64d3768996c6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eada57433b37f759da51ecdb380e530f3fb77fdf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839469"
---
# <a name="idiasectioncontrib"></a>IDiaSectionContrib
Načte data popisující oddíl příspěvek, to znamená, souvislý blok paměti přispěla do bitové kopie kompilace.

## <a name="syntax"></a>Syntaxe

```
IDiaSectionContrib : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaSectionContrib`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaSectionContrib::get_compiland](../../debugger/debug-interface-access/idiasectioncontrib-get-compiland.md)|Získá odkaz na symbol kompilace, které přispěly v této části.|
|[IDiaSectionContrib::get_addressSection](../../debugger/debug-interface-access/idiasectioncontrib-get-addresssection.md)|Načte části část adresy příspěvek.|
|[IDiaSectionContrib::get_addressOffset](../../debugger/debug-interface-access/idiasectioncontrib-get-addressoffset.md)|Načte posunu část adresy příspěvek.|
|[IDiaSectionContrib::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasectioncontrib-get-relativevirtualaddress.md)|Načte obrázek relativní virtuální adresu (RVA) příspěvku.|
|[IDiaSectionContrib::get_virtualAddress](../../debugger/debug-interface-access/idiasectioncontrib-get-virtualaddress.md)|Načte virtuální adresy (VA) příspěvku.|
|[IDiaSectionContrib::get_length](../../debugger/debug-interface-access/idiasectioncontrib-get-length.md)|Získá počet bajtů v oddílu.|
|[IDiaSectionContrib::get_notPaged](../../debugger/debug-interface-access/idiasectioncontrib-get-notpaged.md)|Získá příznak označující, zda část nelze stránkování nedostatek paměti.|
|[IDiaSectionContrib::get_nopad](../../debugger/debug-interface-access/idiasectioncontrib-get-nopad.md)|Získá příznak označující, zda oddílu by neměl bude doplněn na hranici další paměti.|
|[IDiaSectionContrib::get_code](../../debugger/debug-interface-access/idiasectioncontrib-get-code.md)|Získá příznak, který označuje, zda oddíl obsahuje spustitelný kód.|
|[IDiaSectionContrib::get_code16bit](../../debugger/debug-interface-access/idiasectioncontrib-get-code16bit.md)|Získá příznak označující, zda oddíl obsahuje kód 16 bitů.|
|[IDiaSectionContrib::get_initializedData](../../debugger/debug-interface-access/idiasectioncontrib-get-initializeddata.md)|Získá příznak označující, zda oddíl obsahuje inicializovaná data.|
|[IDiaSectionContrib::get_uninitializedData](../../debugger/debug-interface-access/idiasectioncontrib-get-uninitializeddata.md)|Získá příznak, který označuje, zda oddíl obsahuje neinicializovaná data.|
|[IDiaSectionContrib::get_informational](../../debugger/debug-interface-access/idiasectioncontrib-get-informational.md)|Získá příznak označující, zda oddíl obsahuje komentáře nebo podobné informace.|
|[IDiaSectionContrib::get_remove](../../debugger/debug-interface-access/idiasectioncontrib-get-remove.md)|Získá příznak, který určuje, zda je v části odebrat předtím, než je k součástí bitové kopie v paměti.|
|[IDiaSectionContrib::get_comdat](../../debugger/debug-interface-access/idiasectioncontrib-get-comdat.md)|Získá příznak označující, zda je oddíl COMDAT záznam.|
|[IDiaSectionContrib::get_discardable](../../debugger/debug-interface-access/idiasectioncontrib-get-discardable.md)|Získá příznak označující, zda části můžete zahodit.|
|[IDiaSectionContrib::get_notCached](../../debugger/debug-interface-access/idiasectioncontrib-get-notcached.md)|Získá příznak označující, zda část nejde udržovat v mezipaměti.|
|[IDiaSectionContrib::get_share](../../debugger/debug-interface-access/idiasectioncontrib-get-share.md)|Získá příznak, který označuje, zda je možné sdílet části v paměti.|
|[IDiaSectionContrib::get_execute](../../debugger/debug-interface-access/idiasectioncontrib-get-execute.md)|Získá příznak, který určuje, zda je spustitelný soubor jako kód v části.|
|[IDiaSectionContrib::get_read](../../debugger/debug-interface-access/idiasectioncontrib-get-read.md)|Získá příznak označující, zda můžete přečíst v části.|
|[IDiaSectionContrib::get_write](../../debugger/debug-interface-access/idiasectioncontrib-get-write.md)|Získá příznak, který označuje, zda je možné zapisovat části.|
|[IDiaSectionContrib::get_dataCrc](../../debugger/debug-interface-access/idiasectioncontrib-get-datacrc.md)|Načte kontrola cyklické redundance (CRC) dat v oddílu.|
|[IDiaSectionContrib::get_relocationsCrc](../../debugger/debug-interface-access/idiasectioncontrib-get-relocationscrc.md)|Načte CRC přemístění informace oddílu.|
|[IDiaLineNumber::get_compilandId](../../debugger/debug-interface-access/idialinenumber-get-compilandid.md)|Načte identifikátor kompilace pro oddíl.|

## <a name="remarks"></a>Poznámky

## <a name="notes-for-callers"></a>Poznámky pro volající
Toto rozhraní je získán voláním [idiaenumsectioncontribs::Item –](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md) a [idiaenumsectioncontribs::Next –](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md) metody. Zobrazit [idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) rozhraní příklad se dá získat `IDiaSectionContrib` rozhraní.

## <a name="example"></a>Příklad
Tato funkce zobrazí adresu každého oddílu spolu s všechny přidružené symboly. Najdete v článku [idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) rozhraní naleznete v tématu Jak `IDiaSectionContrib` získat rozhraní.

```C++
void PrintSectionContrib(IDiaSectionContrib* pSecContrib, IDiaSession* pSession)
{
    if (pSecContrib != NULL && pSession != NULL)
    {
        DWORD rva;
        if ( pSecContrib->get_relativeVirtualAddress( &rva ) == S_OK )
        {
            printf( "\taddr: 0x%.8X", rva );
            pSecContrib = NULL;
            CComPtr<IDiaSymbol> pSym;
            if ( psession->findSymbolByRVA( rva, SymTagNull, &pSym ) == S_OK )
            {
                CDiaBSTR name;
                DWORD    tag;
                pSym->get_symTag( &tag );
                pSym->get_name( &name );
                printf( "     symbol: %ws (%ws)\n",
                        name != NULL ? name : L"",
                        szTags[ tag ] );
            }
            else
            {
                printf( "<no symbol found?>\n" );
            }
        }
        else
        {
            DWORD isect;
            DWORD offset;
            pSecContrib->get_addressSection( &isect );
            pSecContrib->get_addressOffset( &offset );
            printf( "\taddr: 0x%.4X:0x%.8X", isect, offset );
            pSecContrib = NULL;
            CComPtr<IDiaSymbol> pSym;
            if ( SUCCEEDED( psession->findSymbolByAddr(
                                              isect,
                                              offset,
                                              SymTagNull,
                                              &pSym )
                          )
               )
            {
                CDiaBSTR name;
                DWORD    tag;
                pSym->get_symTag( &tag );
                pSym->get_name( &name );
                printf( "     symbol: %ws (%ws)\n",
                    name != NULL ? name : L"",
                    szTags[ tag ] );
            }
            else
            {
                printf( "<no symbol found?>\n" );
            }
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
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)
- [IDiaEnumSectionContribs::Item](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md)
- [IDiaEnumSectionContribs::Next](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md)
