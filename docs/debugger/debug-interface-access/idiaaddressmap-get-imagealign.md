---
title: Idiaaddressmap::get_imagealign – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::get_imageAlign method
ms.assetid: f1ba8071-669c-4cf7-9ac0-02f26d99f366
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c37d05025f6de870d6011e2abba31cd28f06f780
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaaddressmapgetimagealign"></a>IDiaAddressMap::get_imageAlign
Načte aktuální zarovnání obrázku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_imageAlign (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu zarovnání obrázku z spustitelný soubor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Bitové kopie je zarovnán podle jak bitové kopie byl načteny a vytvořit hranice konkrétní paměti. Zarovnání je obvykle na hranicích 1, 2, 4, 8, 16, 32 nebo 64 bajtů. Zarovnání obrázku lze nastavit pomocí volání [idiaaddressmap::put_imagealign –](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::put_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)