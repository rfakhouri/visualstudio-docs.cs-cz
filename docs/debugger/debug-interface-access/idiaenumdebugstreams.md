---
title: Idiaenumdebugstreams – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams interface
ms.assetid: 611caf4f-7a5f-4aa4-b909-52feeb3cc752
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b17e79e1bfefd5b6b23695f2f49d694c7148ae0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838142"
---
# <a name="idiaenumdebugstreams"></a>IDiaEnumDebugStreams
Vytvoří výčet různé datové proudy debug obsažené ve zdroji dat.

## <a name="syntax"></a>Syntaxe

```
IDiaEnumDebugStreams : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaEnumDebugStreams`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaEnumDebugStreams::get__NewEnum](../../debugger/debug-interface-access/idiaenumdebugstreams-get-newenum.md)|Načte `IEnumVARIANT` verzi výčet.|
|[IDiaEnumDebugStreams::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreams-get-count.md)|Získá počet datových proudů ladění.|
|[IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)|Načte datový proud ladění pomocí indexu.|
|[IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)|Načte zadaný počet datové proudy debug v pořadí výčtu.|
|[IDiaEnumDebugStreams::Skip](../../debugger/debug-interface-access/idiaenumdebugstreams-skip.md)|Vynechá zadaný počet datových proudů ladění sekvenci výčtu.|
|[IDiaEnumDebugStreams::Reset](../../debugger/debug-interface-access/idiaenumdebugstreams-reset.md)|Návrat na začátek sekvence výčtu.|
|[IDiaEnumDebugStreams::Clone](../../debugger/debug-interface-access/idiaenumdebugstreams-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|

## <a name="remarks"></a>Poznámky
Formáty data nedokumentované obsahu datové proudy debug je závislý na implementaci.

## <a name="notes-for-callers"></a>Poznámky pro volající
Volání [idiasession::getenumdebugstreams –](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md) metodu k získání `IDiaEnumDebugStreams` objektu.

## <a name="example"></a>Příklad
Tento příklad ukazuje, jak přistupovat k dispozici datové proudy z tohoto rozhraní. Najdete v článku [idiaenumdebugstreamdata –](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md) rozhraní pro implementaci `PrintStreamData` funkce.

```C++
void DumpAllDebugStreams( IDiaSession* pSession)
{
    IDiaEnumDebugStreams* pEnumStreams;

    wprintf(L"\n\n*** DEBUG STREAMS\n\n");
    // Retrieve an enumerated sequence of debug data streams
    if(pSession->getEnumDebugStreams(&pEnumStreams) == S_OK)
    {
        IDiaEnumDebugStreamData* pStream;
        ULONG celt = 0;

        for(; pEnumStreams->Next(1, &pStream, &celt) == S_OK; pStream = NULL)
        {
            PrintStreamData(pStream);
            pStream->Release();
        }
        pEnumStreams->Release();
    }
    else
    {
        wprintf(L"Failed to get any debug streams!\n");
    }
    wprintf(L"\n");
}
```

## <a name="requirements"></a>Požadavky
Záhlaví: Dia2.h

Knihovna: diaguids.lib

DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
- [IDiaSession::getEnumDebugStreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md)
