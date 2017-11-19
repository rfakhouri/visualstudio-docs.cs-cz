---
title: "Idiaaddressmap::put_addressmapenabled – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaAddressMap::put_addressMapEnabled method
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5542e00511301a84ba54a08405434001f63c4b5d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaaddressmapputaddressmapenabled"></a>IDiaAddressMap::put_addressMapEnabled
Určuje, zda má být použita adres mapují k překladu adres symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT put_addressMapEnabled (   
   BOOL NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 NewVal  
 [v] Nastavte na `TRUE` Povolit překlad symbolů, nebo `FALSE` zakázat.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Spustitelný soubor po procesory někdy aktualizovat spustitelný soubor. DIA obsahuje mechanismus pro podporu překlad symbolů do nového rozložení.  
  
 Při načítání souboru PDB adres mapují uložené v souboru je povoleno. V určitých časech, ale když klientskou aplikaci muset zadat vlastní adres mapují voláním [idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) metoda. Pokud `set_addressMap` metoda je úspěšné, musí volat klientské aplikace `put_addressMapEnabled` metoda s `NewVal` parametr `TRUE` povolit používání tohoto adres mapují.  
  
 Aktuální stav adres mapují zapínání se dá načíst pomocí volání [idiaaddressmap::get_addressmapenabled –](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [Idiaaddressmap::get_addressmapenabled –](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)