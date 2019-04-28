---
title: IDiaSession::findInlineesByName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 9860336d-f703-4ecb-bfc4-3f5beb175a76
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1cb665e3c0965a2e85c8d28202114c95928988d5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839300"
---
# <a name="idiasessionfindinlineesbyname"></a>IDiaSession::findInlineesByName
Načte výčet, který umožňuje klientovi k iteraci v rámci informace o číslech řádků všech vložených funkcí, které odpovídají zadaným názvem.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findInlineesByName ( 
   LPCOLESTR             name,
   DWORD                 option,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>Parametry
 `name`

[in] Určuje název, který má použít pro porovnání.

 `option`

[in] Určení možností porovnání použitý k hledání názvu. Hodnoty z [namesearchoptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md) výčtu lze použít samostatně nebo v kombinaci.

 `ppResult`

[out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objekt, který obsahuje seznam čísel řádků, které byly načteny.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)