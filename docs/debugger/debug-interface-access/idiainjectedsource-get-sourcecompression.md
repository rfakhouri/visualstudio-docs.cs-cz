---
title: Idiainjectedsource::get_sourcecompression – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_sourceCompression method
ms.assetid: 854b142f-23a9-466c-bf7f-98e581d5abcd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 00c7783752a183e8afc580c4c74285add8a51041
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839911"
---
# <a name="idiainjectedsourcegetsourcecompression"></a>IDiaInjectedSource::get_sourceCompression
Načte ukazatel zdroj komprese používá.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_sourceCompression ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí ukazatel zdroj komprese používá. Hodnota nula označuje, že se použil bez komprese zdroje.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Hodnota vrácená touto metodou je specifické pro kompilátor používají. Kompilátor může například používat kódování s délkou spustit nebo Huffmanova – vizuální styl kompresi.

## <a name="see-also"></a>Viz také
- [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)