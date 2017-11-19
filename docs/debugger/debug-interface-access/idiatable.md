---
title: "Idiatable – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaTable interface
ms.assetid: c99a2c44-7b72-4e3c-b963-25fe3df3a555
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be24edc89328f08199316df8bdedf2ab6391907b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiatable"></a>IDiaTable
Vytvoří výčet DIA data zdrojová tabulka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaTable : IEnumUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaTable`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiatable::get__newenum –](../../debugger/debug-interface-access/idiatable-get-newenum.md)|Načte [IEnumVARIANT rozhraní](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) verzi této enumerátor.|  
|[Idiatable::get_Name –](../../debugger/debug-interface-access/idiatable-get-name.md)|Načte název tabulky.|  
|[Idiatable::get_count –](../../debugger/debug-interface-access/idiatable-get-count.md)|Načte počet položek v tabulce.|  
|[Idiatable::Item –](../../debugger/debug-interface-access/idiatable-item.md)|Získá odkaz na konkrétní položku indexu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní implementuje `IEnumUnknown` výčet metod v oboru názvů sestavení Microsoft.VisualStudio.OLE.Interop. `IEnumUnknown` Výčtu rozhraní je mnohem efektivnější pro iterování přes obsahu tabulky než [idiatable::get_count –](../../debugger/debug-interface-access/idiatable-get-count.md) a [idiatable::Item –](../../debugger/debug-interface-access/idiatable-item.md) metody.  
  
 Výklad `IUnknown` rozhraní vrácená z buď `IDiaTable::Item` metoda nebo `Next` – metoda (v oboru názvů sestavení Microsoft.VisualStudio.OLE.Interop) je závislá na typu tabulky. Například pokud `IDiaTable` rozhraní představuje seznam vloženého zdroje `IUnknown` rozhraní mají být získána pro [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat voláním toto rozhraní [idiaenumtables::Item –](../../debugger/debug-interface-access/idiaenumtables-item.md) nebo [idiaenumtables::Next –](../../debugger/debug-interface-access/idiaenumtables-next.md) metody.  
  
 Následující rozhraní je implementováno s `IDiaTable` rozhraní (to znamená, můžete zadat dotaz `IDiaTable` rozhraní pro jednu z následujících rozhraní):  
  
-   [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)  
  
-   [Idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md)  
  
-   [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)  
  
-   [Idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)  
  
-   [Idiaenumsegments –](../../debugger/debug-interface-access/idiaenumsegments.md)  
  
-   [Idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md)  
  
-   [Idiaenumframedata –](../../debugger/debug-interface-access/idiaenumframedata.md)  
  
## <a name="example"></a>Příklad  
 První funkce `ShowTableNames`, zobrazuje názvy všechny tabulky v relaci. Funkce second `GetTable`, vyhledá všechny tabulky pro tabulku, která implementuje rozhraní je zadaný. Třetí funkce `UseTable`, ukazuje způsob použití `GetTable` funkce.  
  
> [!NOTE]
>  `CDiaBSTR`je třída, která zabalí `BSTR` a automaticky zpracovává uvolnění řetězec při vytváření instance ocitne mimo rozsah.  
  
```C++  
void ShowTableNames(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    CComPtr< IDiaTable > pTable;  
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) )  
            && celt == 1 )  
    {  
        CDiaBSTR bstrTableName;  
        if ( pTable->get_name( &bstrTableName ) != 0 )  
        {  
            Fatal( "get_name" );  
        }  
        printf( "Found table: %ws\n", bstrTableName );  
    }  
  
// Searches the list of all tables for a table that supports  
// the specified interface.  Use this function to obtain an  
// enumeration interface.  
HRESULT GetTable(IDiaSession* pSession,  
                 REFIID       iid,  
                 void**       ppUnk)  
{  
    CComPtr<IDiaEnumTables> pEnumTables;  
    HRESULT hResult;  
  
    if (FAILED(pSession->getEnumTables(&pEnumTables)))  
        Fatal("getEnumTables");  
  
    CComPtr<IDiaTable> pTable;  
    ULONG celt = 0;  
    while (SUCCEEDED(hResult = pEnumTables->Next(1, &pTable, &celt)) &&  
           celt == 1)  
    {  
        if (pTable->QueryInterface(iid, (void**)ppUnk) == S_OK)  
        {  
            return S_OK;  
        }  
        pTable = NULL;  
    }  
  
    if (FAILED(hResult))  
        Fatal("EnumTables->Next");  
  
    return E_FAIL;  
}  
  
// This function shows how to use the GetTable function.  
void UseTable(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSegments> pEnumSegments;  
    if (SUCCEEDED(GetTable(pSession, __uuidof(IDiaEnumSegments), &pEnumSegments)))  
    {  
        // Do something with pEnumSegments.  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumtables –](../../debugger/debug-interface-access/idiaenumtables.md)   
 [Idiaenumtables::Item –](../../debugger/debug-interface-access/idiaenumtables-item.md)   
 [Idiaenumtables::Next –](../../debugger/debug-interface-access/idiaenumtables-next.md)