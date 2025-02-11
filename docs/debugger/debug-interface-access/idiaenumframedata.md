---
title: Idiaenumframedata – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData interface
ms.assetid: 2ca7fd5a-b2fa-4b3a-9492-0263eafc435b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: db06efe400106260556d8eab5fd644bbfc27f0c2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62833616"
---
# <a name="idiaenumframedata"></a>IDiaEnumFrameData
Vytvoří výčet různé prvky rámce data obsažená ve zdroji dat.

## <a name="syntax"></a>Syntaxe

```
IDiaEnumFrameData : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaEnumFrameData`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaEnumFrameData::get__NewEnum](../../debugger/debug-interface-access/idiaenumframedata-get-newenum.md)|Načte `IEnumVARIANT Interface` verzi výčet.|
|[IDiaEnumFrameData::get_Count](../../debugger/debug-interface-access/idiaenumframedata-get-count.md)|Získá počet elementů datového rámce.|
|[IDiaEnumFrameData::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)|Načte datový prvek rámce pomocí indexu.|
|[IDiaEnumFrameData::Next](../../debugger/debug-interface-access/idiaenumframedata-next.md)|Načte zadaný počet snímků datové prvky v pořadí výčtu.|
|[IDiaEnumFrameData::Skip](../../debugger/debug-interface-access/idiaenumframedata-skip.md)|Vynechá zadaný počet snímků datových prvků v sekvenci výčtu.|
|[IDiaEnumFrameData::Reset](../../debugger/debug-interface-access/idiaenumframedata-reset.md)|Návrat na začátek sekvence výčtu.|
|[IDiaEnumFrameData::Clone](../../debugger/debug-interface-access/idiaenumframedata-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[IDiaEnumFrameData::frameByRVA](../../debugger/debug-interface-access/idiaenumframedata-framebyrva.md)|Vrátí relativní virtuální adresu (RVA) objektu frame.|
|[IDiaEnumFrameData::frameByVA](../../debugger/debug-interface-access/idiaenumframedata-framebyva.md)|Vrátí objektu frame pomocí virtuální adresy (VA).|

## <a name="remarks"></a>Poznámky

## <a name="notes-for-callers"></a>Poznámky pro volající
Získat z tohoto rozhraní [idiasession::getenumtables –](../../debugger/debug-interface-access/idiasession-getenumtables.md) metody. Podívejte se na příklad podrobnosti.

## <a name="example"></a>Příklad
Tento příklad ukazuje, jak získat ( `GetEnumFrameData` funkce) a použití ( `ShowFrameData` funkce) `IDiaEnumFrameData` rozhraní. Najdete v článku [idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md) rozhraní příklad `PrintFrameData` funkce.

```C++

      IDiaEnumFrameData* GetEnumFrameData(IDiaSession *pSession)
{
    IDiaEnumFrameData* pUnknown    = NULL;
    REFIID             iid         = __uuidof(IDiaEnumFrameData);
    IDiaEnumTables*    pEnumTables = NULL;
    IDiaTable*         pTable      = NULL;
    ULONG              celt        = 0;

    if (pSession->getEnumTables(&pEnumTables) != S_OK)
    {
        wprintf(L"ERROR - GetTable() getEnumTables\n");
        return NULL;
    }
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)
    {
        // There is only one table that matches the given iid
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);
        pTable->Release();
        if (hr == S_OK)
        {
            break;
        }
    }
    pEnumTables->Release();
    return pUnknown;
}

void ShowFrameData(IDiaSession *pSession)
{
    IDiaEnumFrameData* pEnumFrameData = GetEnumFrameData(pSession);;

    if (pEnumFrameData != NULL)
    {
        IDiaFrameData* pFrameData;
        ULONG celt = 0;

        while(pEnumFrameData->Next(1, &pFrameData, &celt) == S_OK &&
              celt == 1)
        {
            PrintFrameData(pFrameData);
            pFrameData->Release();
        }
        pEnumFrameData->Release();
    }
}
```

## <a name="requirements"></a>Požadavky
**Záhlaví:** Dia2.h

**Knihovna:** diaguids.lib

**DLL:** msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
