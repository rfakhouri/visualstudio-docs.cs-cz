---
title: IDiaSession::findAcceleratorInlineesByLinenum | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 12a2f23c42de99e0ea9a9d6c50e2d9aabed589d4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839456"
---
# <a name="idiasessionfindacceleratorinlineesbylinenum"></a>IDiaSession::findAcceleratorInlineesByLinenum
Vrátí výčet symboly pro vložené rámce, které odpovídají zadaným zdrojovým umístěním.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findAcceleratorInlineeLinesByName ( 
   IDiaSymbol*           parent,
   IDiaSourceFile*       file,
   DWORD                 linenum,
   DWORD                 colnum,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>Parametry
 `parent`

[in] `IDiaSymbol` , Který odpovídá zástupné procedury funkce akcelerátoru, které potřebuje pro hledání.

 `file`

[in] `IDiaSourceFile` Umístění zdroje.

 `linenum`

[in] Číslo řádku umístění zdroje.

 `colnum`

[in] Číslo sloupce umístění zdroje.

 `ppResult`

[out] Ukazatel `IDiaEnumLineNumbers` ukazatel rozhraní, který je inicializován s výsledkem.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)