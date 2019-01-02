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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6a973c5ba66dbe63cf0c9751effbfd73c45b5b29
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53963326"
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
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::get_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)