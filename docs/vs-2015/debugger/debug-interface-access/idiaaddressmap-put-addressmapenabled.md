---
title: Idiaaddressmap::put_addressmapenabled – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_addressMapEnabled method
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4f2f7fc6fd512fa121cf96cb64f4ce4b961772e1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198674"
---
# <a name="idiaaddressmapputaddressmapenabled"></a>IDiaAddressMap::put_addressMapEnabled
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje, zda mapování adres má použít k překladu adres symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)
