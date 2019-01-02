---
title: Idiaaddressmap::put_addressmapenabled – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_addressMapEnabled method
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6894cb14d2aee6a4e1999eab38e095911d51360d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53876010"
---
# <a name="idiaaddressmapputaddressmapenabled"></a>IDiaAddressMap::put_addressMapEnabled
Určuje, zda mapování adres má použít k překladu adres symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT put_addressMapEnabled (   
   BOOL NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 NewVal  
 [in] Nastavte na `TRUE` Povolit překlad symbolů, nebo `FALSE` zakázat.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Spustitelný soubor po procesory někdy aktualizovat spustitelný soubor. DIA obsahuje mechanismus pro podporu překladu symboly do nového rozložení.  
  
 Při načítání souboru PDB je povolená mapa adres, které jsou uložené v souboru. Existují však situace, když klientská aplikace může potřebovat dodání vlastní mapa adres voláním [idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) metody. Pokud `set_addressMap` metoda je úspěšná, musí volat klientské aplikace `put_addressMapEnabled` metody `NewVal` parametr `TRUE` chcete povolit použití adresu, která je namapována.  
  
 Aktuální stav mapa adres neodebraly se dá načíst pomocí volání [idiaaddressmap::get_addressmapenabled –](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)