---
title: Idiaenumdebugstreamdata::Item – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreamData::Item method
ms.assetid: 761e61a5-44a6-4d5d-a98e-c2e9b89d2343
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4f4a3e3f668789f98600cd649716413a57b13130
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838503"
---
# <a name="idiaenumdebugstreamdataitem"></a>IDiaEnumDebugStreamData::Item
Načte zadaný záznam.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Item ( 
   DWORD  index,
   DWORD  cbData,
   DWORD* pcbData,
   BYTE   data[]
);
```

#### <a name="parameters"></a>Parametry
 index

[in] Index záznamu, který se má načíst. Index je v rozsahu 0 až `count`-1, kde `count` je vrácený [idiaenumdebugstreamdata::get_count –](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md).

 cbData

[in] Velikost vyrovnávací paměti dat v bajtech.

 pcbData

[out] Vrátí počet bajtů vrácených. Pokud `data` je `NULL`, pak `pcbData` obsahuje celkový počet bajtů dat, které jsou k dispozici v zadaný záznam.

 data[]

[out] Vyrovnávací paměť je vyplní data záznamu datový proud ladění.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_INVALIDARG` pro neplatné parametry a, pokud `index` parametr je mimo rozsah.

## <a name="see-also"></a>Viz také
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
- [IDiaEnumDebugStreamData::Next](../../debugger/debug-interface-access/idiaenumdebugstreamdata-next.md)
- [IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)
- [IDiaEnumDebugStreamData::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md)
- [IDiaEnumDebugStreamData::Skip](../../debugger/debug-interface-access/idiaenumdebugstreamdata-skip.md)