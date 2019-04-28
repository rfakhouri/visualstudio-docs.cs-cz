---
title: Idiasession::findsymbolbytoken – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findSymbolByToken method
ms.assetid: 3c92149c-6eef-454f-86be-66e89557b9e6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f342efce1c05e305a3e55d6372d1862b04b1197
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62827305"
---
# <a name="idiasessionfindsymbolbytoken"></a>IDiaSession::findSymbolByToken
Načte symbol, který obsahuje token Zadaná metadata.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findSymbolByToken ( 
   ULONG        token,
   SymTagEnum   symtag,
   IDiaSymbol** ppSymbol
);
```

#### <a name="parameters"></a>Parametry
 `token`

[in] Určuje token.

 `symtag`

[in] Typ symbolu, která se má najít. Hodnoty pocházejí ze [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) výčtu.

 `ppSymbol`

[out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) načíst objekt představující symbol.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="example"></a>Příklad

```C++
IDiaSymbol* pFunc;
pSession->findSymbolByToken( token, SymTagFunction, &pFunc );
```

## <a name="see-also"></a>Viz také
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)