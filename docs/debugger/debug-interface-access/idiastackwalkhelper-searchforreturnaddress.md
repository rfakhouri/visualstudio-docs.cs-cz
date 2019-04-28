---
title: IDiaStackWalkHelper::searchForReturnAddress | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::searchForReturnAddress method
ms.assetid: 904223b1-6e26-4980-b310-d0b222cdbbbd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 87518257d9cab91976f69dd03c9026b0800a0680
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62837898"
---
# <a name="idiastackwalkhelpersearchforreturnaddress"></a>IDiaStackWalkHelper::searchForReturnAddress
Vyhledá zadaný zásobník snímků pro nejbližší zpáteční adresu funkce.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT searchForReturnAddress( 
   IDiaFrameData*  frame,
   ULONGLONG*      returnAddress
);
```

#### <a name="parameters"></a>Parametry
 `frame`

[in] [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md) objekt, který představuje aktuální rámec zásobníku.

 `returnAddress`

[out] Vrátí nejbližší zpáteční adresu funkce.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)