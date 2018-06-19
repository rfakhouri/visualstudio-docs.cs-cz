---
title: Idiaaddressmap::set_imageheaders – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51b68475b9ef0374f95febabc2997524bfd61259
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31458476"
---
# <a name="idiaaddressmapsetimageheaders"></a>IDiaAddressMap::set_imageHeaders
Nastaví obrázek hlavičky, chcete-li povolit překlad relativní virtuální adresy.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT set_imageHeaders (   
   DWORD cbData,  
   BYTE  data[],  
   BOOL  originalHeaders  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 cbData  
 [v] Počet bajtů dat záhlaví. Musí být `n*sizeof(IMAGE_SECTION_HEADER)` kde `n` je počet záhlaví oddílů ve spustitelném souboru.  
  
 data]  
 [v] Pole `IMAGE_SECTION_HEADER` struktury má být použit jako hlavičky bitové kopie.  
  
 originalHeaders  
 [v] Nastavte na `FALSE` Pokud jsou hlavičky bitové kopie z novou bitovou kopii, `TRUE` Pokud to odpovídá původní bitové kopie před upgrade. Obvykle bude nastaven `TRUE` pouze v kombinaci s volání [idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) metoda.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `IMAGE_SECTION_HEADER` Struktura je deklarován v souboru Winnt.h a představuje formát hlavičky část obrázku ke spustitelnému souboru.  
  
 Výpočty relativní virtuální adresu závisí na `IMAGE_SECTION_HEADER` hodnoty. Obvykle DIA načte z databáze (.pdb) soubor programu. Pokud tyto hodnoty chybí, je DIA nelze vypočítat relativní virtuální adresy a [idiaaddressmap::get_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) metoda vrátí `FALSE`. Klient potom musí volat [idiaaddressmap::put_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) způsob povolení výpočtů relativních virtuální adresy po zadání hlavičkách chybí bitové kopie z bitové kopie sám sebe.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [Idiaaddressmap::get_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)