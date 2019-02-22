---
title: Idiaenumframedata::framebyrva – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::frameByRVA method
ms.assetid: 4b8dec05-e76c-4cc4-9644-2369d583849f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cbdb525034016981c1f9030e6bce1f9590c45591
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607392"
---
# <a name="idiaenumframedataframebyrva"></a>IDiaEnumFrameData::frameByRVA
Vrátí relativní virtuální adresu (RVA) objektu frame.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT frameByRVA( 
   DWORD           relativeVirtualAddress,
   IDiaFrameData** frame
);
```

#### <a name="parameters"></a>Parametry
 relativeVirtualAddress

[in] Adresa RVA rámce, které vás zajímají.

 rámec

[out] Vrátí [idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md) objekt představující rámec, který obsahuje adresu k dispozici.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` pokud neodpovídají žádná data rámec zadané adrese. V opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)