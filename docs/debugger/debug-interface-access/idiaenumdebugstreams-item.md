---
title: Idiaenumdebugstreams::Item – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams::Item method
ms.assetid: 6b388fe1-eabc-4720-9d59-dc09b0ceaeac
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f07ecb151b6bf2cd4a9d48fbe6596bc7a533f97a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838256"
---
# <a name="idiaenumdebugstreamsitem"></a>IDiaEnumDebugStreams::Item
Načte datový proud ladění index nebo název.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Item (
    VARIANT                   index,
    IDiaEnumDebugStreamData** stream
);
```

#### <a name="parameters"></a>Parametry
index

[in] Index nebo název datový proud ladění se má načíst. Pokud varianta celé číslo se používá, musí být v rozsahu 0 až `count`-1, kde `count` je vrácená rozhraním [idiaenumdebugstreams::get_count –](../../debugger/debug-interface-access/idiaenumdebugstreams-get-count.md) metody.

datový proud

[out] Vrátí [idiaenumdebugstreamdata –](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md) reprezentující datový proud ladění zadaného objektu.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="example"></a>Příklad

```C++
IDiaEnumDebugStreamData *GetStreamData(IDiaEnumDebugStreams *pStreamList,
                                       LONG whichStream)
{
    IDiaEnumDebugStreamData *pStreamData = NULL;
    if (pStreamList != NULL)
    {
        LONG numStreams = 0;
        if (pStreamList->get_count(&numStreams) == S_OK &&
            whichStream >= 0 && whichStream < numStreams)
        {
            VARIANT vIndex;
            vIndex.vt   = VT_I4;
            vIndex.lVal = whichStream;
            if (pStreamList->Item(vIndex,&pStreamData) != S_OK)
            {
                std::cerr << "Error retrieving stream " << whichStream << std::endl;
            }
        }
    }
    return(pStreamData);
}
```

## <a name="see-also"></a>Viz také
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
- [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)
