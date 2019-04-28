---
title: Idiasegment – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSegment interface
ms.assetid: 384ae0e1-077e-4d4f-98de-ac43c32c882f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8dfb0330f08dab158c298bbc944d8dc6410f719f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839430"
---
# <a name="idiasegment"></a>IDiaSegment
Mapuje data z část čísla do segmentů adresního prostoru.

## <a name="syntax"></a>Syntaxe

```
IDiaSegment : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaSegment`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaSegment::get_frame](../../debugger/debug-interface-access/idiasegment-get-frame.md)|Získá číslo segmentu.|
|[IDiaSegment::get_offset](../../debugger/debug-interface-access/idiasegment-get-offset.md)|Načte posun v příslušných segmentech, kde začíná v části.|
|[IDiaSegment::get_length](../../debugger/debug-interface-access/idiasegment-get-length.md)|Získá počet bajtů v segmentu.|
|[IDiaSegment::get_read](../../debugger/debug-interface-access/idiasegment-get-read.md)|Získá příznak, který označuje, zda lze číst segmentu.|
|[IDiaSegment::get_write](../../debugger/debug-interface-access/idiasegment-get-write.md)|Získá příznak, který označuje, zda může být upraveno segmentu.|
|[IDiaSegment::get_execute](../../debugger/debug-interface-access/idiasegment-get-execute.md)|Získá příznak, který určuje, zda je spustitelný soubor segmentu.|
|[IDiaSegment::get_addressSection](../../debugger/debug-interface-access/idiasegment-get-addresssection.md)|Získá číslo oddílu, který se mapuje na tento segment.|
|[IDiaSegment::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasegment-get-relativevirtualaddress.md)|Načte relativní virtuální adresu (RVA) začátku části.|
|[IDiaSegment::get_virtualAddress](../../debugger/debug-interface-access/idiasegment-get-virtualaddress.md)|Načte virtuální adresy (VA) začátku části.|

## <a name="remarks"></a>Poznámky
Protože DIA SDK už provádí překlady z část posun relativních virtuálních adres, nebude provádět většinu aplikací pomocí informací na mapě segmentu.

## <a name="notes-for-callers"></a>Poznámky pro volající
Získat voláním toto rozhraní [idiaenumsegments::Item –](../../debugger/debug-interface-access/idiaenumsegments-item.md) nebo [idiaenumsegments::Next –](../../debugger/debug-interface-access/idiaenumsegments-next.md) metody. Podívejte se na příklad podrobnosti.

## <a name="example"></a>Příklad
Tato funkce zobrazí adresu všechny segmenty v tabulce a nejbližší symbol.

```C++
void ShowSegments(IDiaTable *pTable, IDiaSession *pSession)
{
    CComPtr<IDiaEnumSegments> pSegments;
    if ( SUCCEEDED( pTable->QueryInterface(
                                _uuidof( IDiaEnumSegments ),
                               (void**)&pSegments )
                  )
       )
    {
        CComPtr<IDiaSegment> pSegment;
        while ( SUCCEEDED( hr = pSegments->Next( 1, &pSegment, &celt ) ) &&
                celt == 1 )
        {
            DWORD rva;
            DWORD seg;

            pSegment->get_addressSection( &seg );
            if ( pSegment->get_relativeVirtualAddress( &rva ) == S_OK )
            {
                printf( "Segment %i addr: 0x%.8X\n", seg, rva );
                pSegment = NULL;

                CComPtr<IDiaSymbol> pSym;
                if ( psession->findSymbolByRVA( rva, SymTagNull, &pSym ) == S_OK )
                {
                    CDiaBSTR name;
                    DWORD    tag;

                    pSym->get_symTag( &tag );
                    pSym->get_name( &name );
                    printf( "\tClosest symbol: %ws (%ws)\n",
                            name != NULL ? name : L"",
                            szTags[ tag ] );
                }
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
- [IDiaEnumSegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)
- [IDiaEnumSegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)
