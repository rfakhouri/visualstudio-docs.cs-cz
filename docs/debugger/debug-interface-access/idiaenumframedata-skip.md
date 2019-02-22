---
title: Idiaenumframedata::Skip – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Skip method
ms.assetid: 67140b4c-7125-4895-932d-42412326da29
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d747149e18f831b9f57249503a64c37141c4daa
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56598476"
---
# <a name="idiaenumframedataskip"></a>IDiaEnumFrameData::Skip
Vynechá zadaný počet snímků datových prvků v sekvenci výčtu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>Parametry
 celt

[in] Počet datových elementů rámce v pořadí výčtu pro přeskočení.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` Pokud neexistují žádné další záznamy pro přeskočení.

## <a name="see-also"></a>Viz také
- [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)