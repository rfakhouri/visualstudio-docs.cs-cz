---
title: IDiaAddressMap::set_imageHeaders | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 18fa69929f78d5ae661169a09db97697d98f4d94
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198644"
---
# <a name="idiaaddressmapsetimageheaders"></a>IDiaAddressMap::set_imageHeaders
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nastaví obrázek záhlaví povolit překlad relativní virtuální adresu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT set_imageHeaders (   
   DWORD cbData,  
   BYTE  data[],  
   BOOL  originalHeaders  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 cbData  
 [in] Počet bajtů dat záhlaví. Musí být `n*sizeof(IMAGE_SECTION_HEADER)` kde `n` je číslo oddílu záhlaví ve spustitelném souboru.  
  
 data]  
 [in] Pole `IMAGE_SECTION_HEADER` struktury má být použit jako hlavičky bitové kopie.  
  
 originalHeaders  
 [in] Nastavte na `FALSE` Pokud jsou hlavičky bitové kopie z nové image `TRUE` Pokud odrážejí původní obrázkem dříve, než upgrade. Obvykle to se nastavuje `TRUE` pouze v kombinaci s voláními [idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) metody.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `IMAGE_SECTION_HEADER` Struktura je deklarována v souboru Winnt.h a představuje formát obrázku oddíl hlavičky spustitelného souboru.  
  
 Relativní virtuální adresu výpočty závisí na `IMAGE_SECTION_HEADER` hodnoty. Obvykle DIA načte z soubor databáze (PDB) programu. Pokud tyto hodnoty chybí, je DIA nelze vypočítat relativních virtuálních adres a [idiaaddressmap::get_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) vrátí metoda `FALSE`. Klient musíte pak zavolat [idiaaddressmap::put_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) metoda umožňuje relativní virtuální adresu výpočty po zadání chybějící hlavičky bitové kopie ze samotné.  
  
## <a name="see-also"></a>Viz také  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)
