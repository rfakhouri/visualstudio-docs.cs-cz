---
title: Idialoadcallback2::restrictoriginalpathaccess – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictOriginalPathAccess method
ms.assetid: 31fde3af-2824-4b0f-8d0d-cee6046596f6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 26539d4217682b4d5357f13e9f9368c81297da78
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839742"
---
# <a name="idialoadcallback2restrictoriginalpathaccess"></a>IDiaLoadCallback2::RestrictOriginalPathAccess
Určuje, zda je možné najít soubor .pdb v původní adresář ladění.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT RestrictOriginalPathAccess ();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Žádné jiné než návratový kód `S_OK` brání hledá soubor .pdb v původní adresář ladění. Původní adresář ladění je cesta k souboru symbolů, které jsou zkompilovány do spustitelného souboru při ladění je zapnuté. Tato cesta není nutně stejné jako cesta kde spustitelný soubor existuje.

## <a name="see-also"></a>Viz také
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)