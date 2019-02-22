---
title: IDiaSession::findInlineeLinesByRVA | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7a74d5ee-0dbf-47c0-92b4-47ec03b13ce9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 900680fe58ab5061d3f8cca07fa1906cf34f7e5b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642258"
---
# <a name="idiasessionfindinlineelinesbyrva"></a>IDiaSession::findInlineeLinesByRVA
Načte výčet, který umožňuje klientovi k iteraci v rámci o počtu řádků všech funkcí, které jsou vloženy, přímo nebo nepřímo, symbolem zadaný nadřazený prvek a jsou obsaženy v rámci zadaného relativní virtuální adresu (RVA).

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findInlineeLinesByRVA ( 
   IDiaSymbol*           parent,
   DWORD                 rva,
   DWORD                 length,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>Parametry
 `parent`

[in] `IDiaSymbol` Představující nadřazeného objektu.

 `rva`

[in] Určuje adresu jako adresu RVA.

 `length`

[in] Určuje rozsah adres v počet bajtů, aby pokryl s Tento dotaz.

 `ppResult`

[out] Obsahuje `IDiaEnumLineNumbers` objekt, který obsahuje seznam čísel řádků, které jsou načteny.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)