---
title: Idiasession::findlines – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLines method
ms.assetid: d6e84916-fd55-457e-b057-57f97b51fe73
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b127cbc5c9ddc5a2aa2d293d1371bab18d191fdb
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642882"
---
# <a name="idiasessionfindlines"></a>IDiaSession::findLines
Načte čísla řádků v rámci zadaného kompilace a identifikátory zdrojového souboru.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findLines ( 
   IDiaSymbol*           compiland,
   IDiaSourceFile*       file,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>Parametry
 `compiland`

[in] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt představující souboru pro kompilaci. Pomocí tohoto rozhraní jako kontext, ve kterém chcete hledat čísla řádků.

 `file`

[in] [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt představující zdrojový soubor, ve kterém chcete hledat čísla řádků.

 `ppResult`

[out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) načíst objekt, který obsahuje seznam čísel řádků.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)