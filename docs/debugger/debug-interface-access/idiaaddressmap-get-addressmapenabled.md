---
title: Idiaaddressmap::get_addressmapenabled – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::get_addressMapEnabled method
ms.assetid: 6183dc5e-befa-4e5a-ae5a-f4aa24f3ed9e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 225cac39cb56bbf5b03478c6009162c711baad87
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaaddressmapgetaddressmapenabled"></a>IDiaAddressMap::get_addressMapEnabled
Určuje, zda bylo úspěšně navázáno adres mapují konkrétní relace.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_addressMapEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí `TRUE` Pokud je povoleno mapování adresy.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Spustitelný soubor po procesory někdy aktualizovat spustitelný soubor. DIA obsahuje mechanismus pro podporu překlad symbolů do nového rozložení.  
  
 Klientské aplikace můžete nastavit adres mapují konkrétní relace získáním [idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md) rozhraní z [idiasession –](../../debugger/debug-interface-access/idiasession.md) rozhraní a volání [IDiaAddressMap::set_ addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) metoda následuje volání [idiaaddressmap::put_addressmapenabled –](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) metoda. `get_addressMapEnabled` Metoda vrátí výsledky volání `put_addressMapEnabled` metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)