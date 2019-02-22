---
title: Idiasymbol::get_isltcg – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b674e99bcb9bd621808b080fffa6873f96cfb707
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611786"
---
# <a name="idiasymbolgetisltcg"></a>IDiaSymbol::get_isLTCG
Získá příznak, který určuje, zda [Kompilantu](../../debugger/debug-interface-access/compiland.md) bylo propojeno pomocí přepínače linkeru [parametru/LTCG (generování kódu při propojování odkaz)](/cpp/build/reference/ltcg-link-time-code-generation), což pomáhá při optimalizaci celého programu. Tento přepínač platí pouze pro spravovaný kód.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_iSLTCG(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Parametry
 pFlag

[out] Vrátí `TRUE` Pokud `compiland` bylo propojeno pomocí přepínače linkeru parametru/LTCG; v opačném případě vrátí `FALSE`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="requirements"></a>Požadavky

|Požadavek|Popis|
|-----------------|-----------------|
|Záhlaví:|dia2.h|
|Verze:|Ve verzi 8.0 DIA SDK|

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)