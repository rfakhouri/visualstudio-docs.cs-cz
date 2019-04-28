---
title: Idiastackwalkhelper::imageforva – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper::imageForVA method
ms.assetid: 8d4edabf-3c01-4fef-8b61-4779f3371067
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56f71364f28bec56c058a52f5a9e79c6bba298b8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62837950"
---
# <a name="idiastackwalkhelperimageforva"></a>IDiaStackWalkHelper::imageForVA
Vrátí začátek pro spustitelný soubor bitové kopie v paměti zadané virtuální adresy někde v paměti ke spustitelnému souboru.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT imageForVA(
   ULONGLONG  vaContext,
   ULONGLONG *pvaImageStart
);
```

#### <a name="parameters"></a>Parametry
 `vaContext`

[in] Virtuální adresa, která je někde v prostoru ke spustitelnému souboru.

 `pvaImageStart`

[out] Vrátí počáteční virtuální adresu ke spustitelnému souboru obrázku.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)