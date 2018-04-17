---
title: Idiaaddressmap::get_relativevirtualaddressenabled – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::get_relativeVirtualAddressEnabled method
ms.assetid: 4c48af81-7148-4d9a-818e-dbe62cbfc638
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3c0875560668f79dca705200a222f9ccadc3003f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaaddressmapgetrelativevirtualaddressenabled"></a>IDiaAddressMap::get_relativeVirtualAddressEnabled
Určuje, zda je povoleno výpočet a použít relativní virtuální adresy (RVA).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_relativeVirtualAddressEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí `TRUE` Pokud výpočtu RVAs je povolená.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 RVAs jsou povoleny, pokud segmentů byla původně načtený ze souboru PDB. Použití RVAs lze dočasně zakázat pomocí volání [idiaaddressmap::put_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) metoda.  
  
 Také lze navázat nová záhlaví image voláním [idiaaddressmap::set_imageheaders –](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) metoda následuje volání `put_relativeVirtualAddressEnabled` metoda povolit používání RVAs pomocí na záhlaví nového bitové kopie.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::set_imageheaders –](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)