---
title: Idiasymbol::get_machinetype – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_machineType method
ms.assetid: 30870b10-6f32-45c6-a0d7-020dea707710
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83156630aee0727502894b286f8c6823e25a5fe9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399269"
---
# <a name="idiasymbolgetmachinetype"></a>IDiaSymbol::get_machineType
Načte typ cíle procesoru.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_machineType ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí hodnotu z [cv_cpu_type_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md) výčet, který určuje cílový typ procesoru.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="see-also"></a>Viz také
- [CV_CPU_TYPE_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)