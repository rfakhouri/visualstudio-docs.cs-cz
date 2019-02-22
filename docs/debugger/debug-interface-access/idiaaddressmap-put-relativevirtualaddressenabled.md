---
title: Idiaaddressmap::put_relativevirtualaddressenabled – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_relativeVirtualAddressEnabled method
ms.assetid: 767c078e-8ad7-4940-9e00-cae7704aadee
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 371db781cae5c988e6c8ff4c4776c5f43d6f047a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607262"
---
# <a name="idiaaddressmapputrelativevirtualaddressenabled"></a>IDiaAddressMap::put_relativeVirtualAddressEnabled
Umožňuje klientovi k povolení nebo zakázání výpočtu a používání relativních virtuálních adres (RVA).

## <a name="syntax"></a>Syntaxe

```C++
HRESULT put_relativeVirtualAddressEnabled ( 
   BOOL NewVal
);
```

#### <a name="parameters"></a>Parametry
 NewVal

[in] Nastavte na `TRUE` chcete povolit, nebo `FALSE` zakázat.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Adresy pro ladění objekty popsané DIA rozhraní a vzhledem k základní, bitové kopie spustitelný soubor se dá načíst jako relativních virtuálních adres.

 Použití RVA je povoleno, když segmenty se nejdřív načíst ze souboru PDB. Chcete-li získat aktuální stav pomocí RVA, zavolejte [idiaaddressmap::get_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) metody.

 `put_relativeVirtualAddress` Povolení RVA po úspěšném volání musí být volána metoda [idiaaddressmap::set_imageheaders –](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) metoda stal nové hlavičky bitové kopie.

## <a name="see-also"></a>Viz také
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)
- [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)