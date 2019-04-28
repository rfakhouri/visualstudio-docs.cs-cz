---
title: IDiaSession::symsAreEquiv | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0253104cf29e86825fadc8c8bd18133e0d3cf593
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839072"
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
Kontroluje, jestli dva symboly jsou ekvivalentní.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT symsAreEquiv ( 
   IDiaSymbol* symbolA,
   IDiaSymbol* symbolB
);
```

#### <a name="parameters"></a>Parametry
 `symbolA`

[in] První [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objektu při porovnání použit.

 `symbolB`

[in] Druhá `IDiaSymbol` objektu při porovnání použit.

## <a name="return-value"></a>Návratová hodnota
 Pokud jsou tyto symboly ekvivalentní, vrátí `S_OK`; v opačném případě vrátí `S_FALSE`, symboly nejsou ekvivalentní. V opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)