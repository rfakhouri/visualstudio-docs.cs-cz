---
title: "Idialinenumber – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLineNumber interface
ms.assetid: 1071f7d0-1f8c-4384-933f-c49c7eb930bd
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45996e66500ebf275154553774d5116c6075af0f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idialinenumber"></a>IDiaLineNumber
Informace přístupů, které popisuje proces mapování z bloku bajtů image textu číslo řádku zdrojového souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaLineNumber : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaLineNumber`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idialinenumber::get_compiland –](../../debugger/debug-interface-access/idialinenumber-get-compiland.md)|Získá odkaz na symbol pro kompilace, která podílí bajtů textu bitové kopie.|  
|[Idialinenumber::get_sourcefile –](../../debugger/debug-interface-access/idialinenumber-get-sourcefile.md)|Získá odkaz na objekt zdrojového souboru.|  
|[Idialinenumber::get_linenumber –](../../debugger/debug-interface-access/idialinenumber-get-linenumber.md)|Načte číslo řádku ve zdrojovém souboru.|  
|[Idialinenumber::get_linenumberend –](../../debugger/debug-interface-access/idialinenumber-get-linenumberend.md)|Načte číslo řádku založené na jeden zdroj, které končí příkaz nebo výraz.|  
|[Idialinenumber::get_columnnumber –](../../debugger/debug-interface-access/idialinenumber-get-columnnumber.md)|Načte číslo sloupce, které začíná výraz nebo příkaz.|  
|[Idialinenumber::get_columnnumberend –](../../debugger/debug-interface-access/idialinenumber-get-columnnumberend.md)|Načte číslo sloupce, které končí výraz nebo příkaz.|  
|[Idialinenumber::get_addresssection –](../../debugger/debug-interface-access/idialinenumber-get-addresssection.md)|Načte část oddílu adresa paměti, kde začíná blok.|  
|[Idialinenumber::get_addressoffset –](../../debugger/debug-interface-access/idialinenumber-get-addressoffset.md)|Načte posunutí část adresy paměti, kde začíná blok.|  
|[Idialinenumber::get_relativevirtualaddress –](../../debugger/debug-interface-access/idialinenumber-get-relativevirtualaddress.md)|Načte obrázek relativní virtuální adresy (RVA) blok.|  
|[Idialinenumber::get_virtualaddress –](../../debugger/debug-interface-access/idialinenumber-get-virtualaddress.md)|Načte virtuální adresy (VA) bloku.|  
|[Idialinenumber::get_length –](../../debugger/debug-interface-access/idialinenumber-get-length.md)|Získá počet bajtů v bloku.|  
|[Idialinenumber::get_sourcefileid –](../../debugger/debug-interface-access/idialinenumber-get-sourcefileid.md)|Načte identifikátor jedinečný zdroj souborů pro zdrojový soubor, který podílí tohoto řádku.|  
|[Idialinenumber::get_statement –](../../debugger/debug-interface-access/idialinenumber-get-statement.md)|Získá příznak označující, že tyto informace řádku popisuje začátku prohlášení ve zdroji programu.|  
|[Idialinenumber::get_compilandid –](../../debugger/debug-interface-access/idialinenumber-get-compilandid.md)|Načte jedinečný identifikátor pro kompilace, která podílí tohoto řádku.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat voláním toto rozhraní [idiaenumlinenumbers::Item –](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md) nebo [idiaenumlinenumbers::Next –](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md) metody.  
  
## <a name="example"></a>Příklad  
 Následující funkce zobrazuje čísla řádků použít ve funkci (reprezentována `pSymbol`).  
  
```C++  
void dumpFunctionLines( IDiaSymbol* pSymbol, IDiaSession* pSession )  
{  
    ULONGLONG length = 0;  
    DWORD     isect  = 0;  
    DWORD     offset = 0;  
  
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
                                      &pLines)  
                      )  
           )  
        {  
            CComPtr< IDiaLineNumber > pLine;  
            DWORD celt      = 0;  
            bool  firstLine = true;  
  
            while ( SUCCEEDED( pLines->Next( 1, &pLine, &celt ) ) &&  
                    celt == 1 )  
            {  
                DWORD offset;  
                DWORD seg;  
                DWORD linenum;  
                CComPtr< IDiaSymbol >     pComp;  
                CComPtr< IDiaSourceFile > pSrc;  
  
                pLine->get_compiland( &pComp );  
                pLine->get_sourceFile( &pSrc );  
                pLine->get_addressSection( &seg );  
                pLine->get_addressOffset( &offset );  
                pLine->get_lineNumber( &linenum );  
                printf( "\tline %d at 0x%x:0x%x\n", linenum, seg, offset );  
                pLine = NULL;  
                if ( firstLine )  
                {  
                    // sanity check  
                    CComPtr< IDiaEnumLineNumbers > pLinesByLineNum;  
                    if ( SUCCEEDED( pSession->findLinesByLinenum(  
                                                  pComp,  
                                                  pSrc,  
                                                  linenum,  
                                                  0,  
                                                  &pLinesByLineNum)  
                                  )  
                       )  
                    {  
                        CComPtr< IDiaLineNumber > pLine;  
                        DWORD celt;  
                        while ( SUCCEEDED( pLinesByLineNum->Next( 1, &pLine, &celt ) ) &&  
                                celt == 1 )  
                        {  
                            DWORD offset;  
                            DWORD seg;  
                            DWORD linenum;  
  
                            pLine->get_addressSection( &seg );  
                            pLine->get_addressOffset( &offset );  
                            pLine->get_lineNumber( &linenum );  
                            printf( "\t\tfound line %d at 0x%x:0x%x\n", linenum, seg, offset );  
                            pLine = NULL;  
                       }  
                    }  
                    firstLine = false;  
                }  
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
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [Idiaenumlinenumbers::Item –](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md)   
 [Idiaenumlinenumbers::Next –](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md)