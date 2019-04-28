---
title: Idiaframedata::get_cplusplusexceptionhandling – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_cplusplusExceptionHandling method
ms.assetid: 54ee9cde-ce8e-45f1-809c-6fbad800d850
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 31b386ff2c31937efc352049f7db068f49e4ba19
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62832758"
---
# <a name="idiaframedatagetcplusplusexceptionhandling"></a>IDiaFrameData::get_cplusplusExceptionHandling
Získá příznak, který určuje, zda zpracování výjimek jazyka C++ je v platnosti.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_cplusplusExceptionHandling ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí `TRUE` Pokud C++ zpracování výjimek je v platnosti; v opačném případě vrátí `FALSE`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Určete, jestli strukturované výjimky je v platnosti zpracování (což se velmi liší od C++ zpracování výjimek), volání [idiaframedata::get_systemexceptionhandling –](../../debugger/debug-interface-access/idiaframedata-get-systemexceptionhandling.md) metoda.

## <a name="see-also"></a>Viz také
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
- [IDiaFrameData::get_systemExceptionHandling](../../debugger/debug-interface-access/idiaframedata-get-systemexceptionhandling.md)