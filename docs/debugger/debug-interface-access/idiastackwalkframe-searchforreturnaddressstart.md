---
title: Idiastackwalkframe::searchforreturnaddressstart – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::searchForReturnAddressStart method
ms.assetid: 47660b9b-6e4f-4dfa-88ab-63dce28f7412
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf7de77016f5ccc15f2cea8bf3172321dd824096
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838051"
---
# <a name="idiastackwalkframesearchforreturnaddressstart"></a>IDiaStackWalkFrame::searchForReturnAddressStart
Vyhledá zadaný zásobník snímků pro zpáteční adresu na nebo blízko ní zadané adrese.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT searchForReturnAddressStart ( 
   IDiaFrameData* frame,
   ULONGLONG      startAddress,
   ULONGLONG*     returnAddress
);
```

#### <a name="parameters"></a>Parametry
 `frame`

[in] [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md) objekt, který představuje aktuální rámec zásobníku.

 `startAddress`

[in] Virtuální paměť adresa, ze kterého má být prohledávání.

 `returnAddress`

[out] Vrátí funkci nejbližší zpětná adresa `startAddress`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)