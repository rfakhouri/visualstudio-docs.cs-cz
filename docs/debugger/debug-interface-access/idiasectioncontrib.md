---
title: "Idiasectioncontrib – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSectionContrib interface
ms.assetid: 371d40f6-ca0e-4d7e-9210-64d3768996c6
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f7effcc96286fc548b42c810789d1cb902bb3c18
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasectioncontrib"></a>IDiaSectionContrib
Načte data popisující část příspěvku, tedy blok souvislé paměti přispěli k bitové kopii kompilace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaSectionContrib : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaSectionContrib`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiasectioncontrib::get_compiland –](../../debugger/debug-interface-access/idiasectioncontrib-get-compiland.md)|Získá odkaz na symbol kompilace, která podílí v této části.|  
|[Idiasectioncontrib::get_addresssection –](../../debugger/debug-interface-access/idiasectioncontrib-get-addresssection.md)|Načte část oddílu příspěvku na adresu.|  
|[Idiasectioncontrib::get_addressoffset –](../../debugger/debug-interface-access/idiasectioncontrib-get-addressoffset.md)|Načte posunutí součástí příspěvku na adresu.|  
|[Idiasectioncontrib::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasectioncontrib-get-relativevirtualaddress.md)|Načte obrázek relativní virtuální adresy (RVA) příspěvku.|  
|[Idiasectioncontrib::get_virtualaddress –](../../debugger/debug-interface-access/idiasectioncontrib-get-virtualaddress.md)|Načte virtuální adresy (VA) příspěvku.|  
|[Idiasectioncontrib::get_length –](../../debugger/debug-interface-access/idiasectioncontrib-get-length.md)|Získá počet bajtů v části.|  
|[Idiasectioncontrib::get_notpaged –](../../debugger/debug-interface-access/idiasectioncontrib-get-notpaged.md)|Získá příznak označující, zda v části nelze stránkování nedostatek paměti.|  
|[Idiasectioncontrib::get_nopad –](../../debugger/debug-interface-access/idiasectioncontrib-get-nopad.md)|Získá příznak označující, zda v části nesmí odsazenou na další hranice paměti.|  
|[Idiasectioncontrib::get_code –](../../debugger/debug-interface-access/idiasectioncontrib-get-code.md)|Načte příznak, který označuje, zda oddíl obsahuje spustitelný kód.|  
|[Idiasectioncontrib::get_code16bit –](../../debugger/debug-interface-access/idiasectioncontrib-get-code16bit.md)|Získá příznak označující, zda oddíl obsahuje kód 16 bitů.|  
|[Idiasectioncontrib::get_initializeddata –](../../debugger/debug-interface-access/idiasectioncontrib-get-initializeddata.md)|Získá příznak označující, zda oddíl obsahuje inicializovaného data.|  
|[Idiasectioncontrib::get_uninitializeddata –](../../debugger/debug-interface-access/idiasectioncontrib-get-uninitializeddata.md)|Získá příznak označující, zda oddíl obsahuje Neinicializovaný data.|  
|[Idiasectioncontrib::get_informational –](../../debugger/debug-interface-access/idiasectioncontrib-get-informational.md)|Získá příznak označující, zda oddíl obsahuje komentáře nebo podobné informace.|  
|[Idiasectioncontrib::get_remove –](../../debugger/debug-interface-access/idiasectioncontrib-get-remove.md)|Načte příznak, který určuje, zda je v části odebrat předtím, než je k součástí bitové kopie v paměti.|  
|[Idiasectioncontrib::get_comdat –](../../debugger/debug-interface-access/idiasectioncontrib-get-comdat.md)|Získá příznak označující, zda je daný oddíl sekvence COMDAT záznam.|  
|[Idiasectioncontrib::get_discardable –](../../debugger/debug-interface-access/idiasectioncontrib-get-discardable.md)|Získá příznak označující, zda může být vymazány části.|  
|[Idiasectioncontrib::get_notcached –](../../debugger/debug-interface-access/idiasectioncontrib-get-notcached.md)|Získá příznak označující, zda v části nelze uložit do mezipaměti.|  
|[Idiasectioncontrib::get_share –](../../debugger/debug-interface-access/idiasectioncontrib-get-share.md)|Získá příznak označující, zda je možné sdílet v části v paměti.|  
|[Idiasectioncontrib::get_execute –](../../debugger/debug-interface-access/idiasectioncontrib-get-execute.md)|Získá příznak označující, zda je daný oddíl spustitelného souboru jako kód.|  
|[Idiasectioncontrib::get_read –](../../debugger/debug-interface-access/idiasectioncontrib-get-read.md)|Získá příznak označující, zda mohou být čteny v části.|  
|[Idiasectioncontrib::get_write –](../../debugger/debug-interface-access/idiasectioncontrib-get-write.md)|Získá příznak označující, zda může být napsán v části.|  
|[Idiasectioncontrib::get_datacrc –](../../debugger/debug-interface-access/idiasectioncontrib-get-datacrc.md)|Načte kontrolu cyklické redundance (CRC) dat v části.|  
|[Idiasectioncontrib::get_relocationscrc –](../../debugger/debug-interface-access/idiasectioncontrib-get-relocationscrc.md)|Načte CRC přemístění informace pro oddíl.|  
|[Idialinenumber::get_compilandid –](../../debugger/debug-interface-access/idialinenumber-get-compilandid.md)|Načte identifikátor kompilace pro oddíl.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní se získá voláním [idiaenumsectioncontribs::Item –](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md) a [idiaenumsectioncontribs::Next –](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md) metody. Najdete v článku [idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) rozhraní pro získání příklad `IDiaSectionContrib` rozhraní.  
  
## <a name="example"></a>Příklad  
 Tato funkce zobrazuje adresu každého oddílu společně s všechny přidružené symboly. Najdete v článku [idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) rozhraní najdete v části Jak `IDiaSectionContrib` se získávají rozhraní.  
  
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
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)   
 [Idiaenumsectioncontribs::Item –](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md)   
 [Idiaenumsectioncontribs::Next –](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md)