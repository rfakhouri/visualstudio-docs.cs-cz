---
title: "Idiaaddressmap::set_imageheaders – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 74556e2e67478cef9b495d3740dc910b62cc8293
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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