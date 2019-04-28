---
title: Idialinenumber::get_sourcefileid – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_sourceFileId method
ms.assetid: 4f482a1e-e85f-4173-98de-8e5f7622554b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be0fffc1c52c6e15e4ac564cb3e53c60a3670c22
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839807"
---
# <a name="idialinenumbergetsourcefileid"></a>IDiaLineNumber::get_sourceFileId
Načte identifikátor jedinečný zdrojového souboru pro zdrojový soubor, který uživatel tento řádek.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_sourceFileId ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí identifikátor souboru jedinečný zdroj pro zdrojový soubor, který uživatel tento řádek.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)