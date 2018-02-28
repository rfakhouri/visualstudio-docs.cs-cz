---
title: "Idiaaddressmap::set_addressmap – | Microsoft Docs"
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
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 681e0bae46497d9b581e89340069937370831777
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiaaddressmapsetaddressmap"></a>IDiaAddressMap::set_addressMap
Poskytuje mapování adres pro podporu rozložení překlady bitovou kopii.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cbData`  
 [v] Počet elementů ve `data` parametr.  
  
 `data[]`  
 [v] Pole [diaaddressmapentry – struktura](../../debugger/debug-interface-access/diaaddressmapentry.md) struktury, které definují překlad mapy.  
  
 `imagetoSymbols`  
 [v] `TRUE` Pokud `data` parametr definuje mapování z nové rozložení obrázku na původní rozložení (jak je popsáno ve symboly ladění). `FALSE`Pokud `data` je mapu, která novou bitovou kopii rozložení prováděné z původní rozložení.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Obvykle DIA načte mapy překlad adres ze souboru databáze (.pdb) programu. Pokud chybí, jsou tyto hodnoty [idiaaddressmap::set_imageheaders –](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) metoda je volána dvakrát, jednou pro `imagetoSymbols` parametr nastaven na `TRUE` a jednou pro `imagetoSymbols` parametr nastaven na `FALSE`. Překlady adres mapy nelze povolit pomocí [idiaaddressmap::put_addressmapenabled –](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) metoda Pokud jsou k dispozici obě překlad mapy.  
  
## <a name="see-also"></a>Viz také  
 [Diaaddressmapentry – struktura](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::put_addressmapenabled –](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)