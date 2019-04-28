---
title: Idiasectioncontrib::get_comdat – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_comdat method
ms.assetid: 8bd9be8d-59ee-4698-b055-daba354b8dcc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 49502c0d693c7a309da9756f73c34df361b7d7bb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62832523"
---
# <a name="idiasectioncontribgetcomdat"></a>IDiaSectionContrib::get_comdat
Získá příznak označující, zda je oddíl COMDAT záznam.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_comdat ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí `TRUE` oddíl je záznam sekvencí COMDAT; v opačném případě vrátí `FALSE`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Záznam sekvencí COMDAT je záznam Common Object File Format (COFF), který zviditelní zabalené funkce pro linker.

## <a name="see-also"></a>Viz také
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)