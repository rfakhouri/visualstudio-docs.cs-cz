---
title: Idiatable – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable interface
ms.assetid: c99a2c44-7b72-4e3c-b963-25fe3df3a555
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f3ca5cc1806aa1b53a3646c1b67320037ed56983
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227287"
---
# <a name="idiatable"></a>IDiaTable
Vytvoří výčet tabulky zdroje dat DIA.

## <a name="syntax"></a>Syntaxe

```
IDiaTable : IEnumUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaTable`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaTable::get__NewEnum](../../debugger/debug-interface-access/idiatable-get-newenum.md)|Načte [rozhraní IEnumVARIANT](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ienumvariant) verzi výčet.|
|[IDiaTable::get_name](../../debugger/debug-interface-access/idiatable-get-name.md)|Načte název tabulky.|
|[IDiaTable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md)|Získá počet položek v tabulce.|
|[IDiaTable::Item](../../debugger/debug-interface-access/idiatable-item.md)|Získá odkaz na příslušnou položku indexu.|

## <a name="remarks"></a>Poznámky
Implementuje toto rozhraní `IEnumUnknown` výčet metody v oboru názvů sestavení Microsoft.VisualStudio.OLE.Interop. `IEnumUnknown` Výčet rozhraní je mnohem efektivnější pro iterování celého obsahu, než [idiatable::get_count –](../../debugger/debug-interface-access/idiatable-get-count.md) a [idiatable::Item –](../../debugger/debug-interface-access/idiatable-item.md) metody.

Výklad `IUnknown` rozhraní vrátí buď z `IDiaTable::Item` metoda nebo `Next` – metoda (v oboru názvů sestavení Microsoft.VisualStudio.OLE.Interop) závisí na typu tabulky. Například pokud `IDiaTable` rozhraní představuje seznam vloženého zdroje `IUnknown` rozhraní mají být získána pro [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
Získat voláním toto rozhraní [idiaenumtables::Item –](../../debugger/debug-interface-access/idiaenumtables-item.md) nebo [idiaenumtables::Next –](../../debugger/debug-interface-access/idiaenumtables-next.md) metody.

Následující rozhraní jsou implementovány pomocí `IDiaTable` rozhraní (to znamená, můžete zadat dotaz `IDiaTable` rozhraní pro jednu z následujících rozhraní):

- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)

- [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)

- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)

- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)

- [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)

- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)

- [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)

## <a name="example"></a>Příklad
První funkce `ShowTableNames`, zobrazuje názvy všechny tabulky v relaci. Druhá funkce `GetTable`, prohledá všechny tabulky pro tabulku, která implementuje rozhraní zadané. Třetí funkce `UseTable`, ukazuje způsob použití `GetTable` funkce.

> [!NOTE]
> `CDiaBSTR` je třída, která zabalí `BSTR` a automaticky zpracovává uvolnění řetězec při vytváření instance dostane mimo rozsah.

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

DLL: msdia80.dll

## <a name="see-also"></a>Viz také
[Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)  
[IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)  
[IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)  
[IDiaEnumTables::Next](../../debugger/debug-interface-access/idiaenumtables-next.md)
